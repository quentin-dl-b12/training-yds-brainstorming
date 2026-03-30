# Hands-On Exercise — Facilitator Guide
### Block 8 of the "AI in SDLC/SSDLC Workflows" Workshop

---

## What this document is

A standalone guide for the presenter running Block 8. It covers the intent of the exercise, what is in the repository, how to facilitate each phase, what to watch for, and how to debrief effectively.

Reading time: ~10 minutes.

---

## The big picture

By the time attendees reach Block 8, they have spent roughly 80 minutes seeing AI tools used in real SSDLC workflows. This block converts observation into experience.

The exercise has one goal: **make the difference between vibe coding and spec-driven development felt, not just understood.**

"Vibe coding" means prompting an AI tool with no upfront structure — just intent and instinct. Spec-driven means having a deliberate conversation about requirements *before* writing a line of code. Both approaches use AI. The difference is what happens before the first prompt.

The exercise is not about finishing the feature. It is about awareness: did you stop to think about what the requirements were *not* saying?

---

## The exercise in one sentence

Attendees implement the same password reset feature twice — once with no constraints (Round 1, vibe coding), once after an agent-assisted requirements review (Round 2, spec-driven) — and compare the results.

---

## The repository

**`quentin-dl-b12/yds-training-exercises`**

Attendees should either clone this in advance or receive a pre-cloned copy. The Python version is in the root folder.

### File overview

| File | Purpose | Attendees modify? |
|---|---|---|
| `requirements.md` | Three user stories for a password reset feature | No — read only |
| `helpers.py` | Shared utilities: database mock, email mock, logger | No — do not modify |
| `app.py` | Round 1 starting file (vibe coding) | Yes |
| `app_2.py` | Round 2 starting file (spec-driven) | Yes |

### What is already implemented

Both `app.py` and `app_2.py` come with working `/register` and `/login` endpoints. Attendees do not touch these.

The following are left as stubs for attendees to implement:

- `POST /reset-password/request` — accepts `{ "email": "..." }`, should generate a token, call `send_reset_email`, and return a generic confirmation message
- `POST /reset-password/confirm` — accepts `{ "token": "...", "new_password": "..." }`, should validate the token and update the user's password in the database
- `create_reset_token(email)` — creates a signed JWT encoding the email address
- `decode_reset_token(token)` — decodes and validates a JWT, returns the email

`helpers.py` provides:
- `db` — a `DocumentStore` instance (in-memory dict-backed mock database). Pre-seeded with `alice@example.com` and `bob@example.com`.
- `send_reset_email(address, token)` — prints the token to stdout (mock). In Round 1, attendees discover this during implementation. In Round 2, the agent conversation may flag what a real implementation needs.
- `logger` — a pre-configured Python logger.

### The intentional traps in the existing code

The existing `/register` and `/login` implementations contain deliberate vulnerabilities. Attendees are not told about these — they are there as background realism and as material for the debrief if the conversation goes there.

| Location | What it does | OWASP category |
|---|---|---|
| `hash_password()` | Uses MD5 instead of bcrypt/argon2 | A02 — Cryptographic Failures |
| `/register` | Logs the raw plaintext password | A09 — Security Logging Failures |
| `/login` | Returns different error messages for "email not found" vs "wrong password" | A07 — Identification and Authentication Failures (account enumeration) |
| `/login` | No account lockout or rate limiting | A07 |

### The intentional gaps in `requirements.md`

The user stories look credible — they mention "secure tokens" and "hashed passwords." But they are deliberately silent on six security requirements:

| Gap | OWASP category |
|---|---|
| Tokens have no expiry (TTL) | A07 |
| Tokens can be reused indefinitely (no single-use invalidation) | A07 |
| No rate limiting on the request endpoint | A04 — Insecure Design |
| No enumeration protection (endpoint reveals whether email exists) | A07 |
| No audit logging for reset attempts | A09 |
| Token stored as plaintext in the database | A02 |

A well-prompted AI agent in Round 2 will surface most of these. This is the exercise's core demonstration.

---

## How to run it

### Before the session

Actually running the code is not required for the exercise. The focus is on the AI journey, not the final product. But in case the participants want to run the code, here are the setup steps:

- Verify the repo is cloneable and the pip dependencies install cleanly (`fastapi`, `python-jose`, `uvicorn`, `pydantic`)
- Run `python app.py` once to confirm the server starts on port 2626
- Have a REST client ready (curl, Insomnia, or the FastAPI `/docs` Swagger UI at `http://localhost:2626/docs`)

### Slide to show at the start of Block 8

The slides list the two-round structure with the repo URL and the four files to open. No further instruction is given at this point — the exercise is designed to start with minimal scaffolding.

---

### Setup — 5 min

Ask everyone to open the repo in their IDE. Ask them to read the README and `requirements.md` first.

While they do this, set the frame out loud:

> "This is a real FastAPI application. `/register` and `/login` already work. Your job is to implement password reset. You have the user stories. You have the helper utilities. The rest is up to you and your AI tool."

Take questions about the tech stack only (FastAPI, how to run, where to find the Swagger UI). Do not answer questions about what the implementation should look like.

---

### Round 1 — Vibe Coding — 15 min

Attendees work in `app.py`. No rules. No prompt structure. Just implement.

**Your job during this round:**
- Walk the room. Observe what prompts people write.
- Stay silent on security. If someone asks "should I validate the token?", answer: "What do you think the requirements say?"
- Note interesting approaches — very short implementations, very long ones, anyone who thinks to add expiry, anyone who skips token validation entirely. These are gold for the debrief.

The goal is **not** to have a working, secure implementation at the end. The goal is to have an implementation shaped purely by instinct and what the AI tool offered.

---

### Debrief 1 — 5 min

Do not show answers. Ask these three questions and let the answers sit:

1. "Did your implementation handle the case where the email doesn't exist? What does it return?"
2. "Can the same reset token be used twice? Three times?"
3. "What's inside your JWT? Does it expire?"

You want a mix of "yes", "no", and "I didn't think about that." That mix is the setup for Round 2.

> Do not resolve the tension yet. The point is to make people curious, not to make them feel corrected.

---

### Round 2 — Spec-Driven — 20 min

Attendees switch to `app_2.py`. Before writing any code, they must open a conversation with their AI agent and ask it to review `requirements.md` and identify what is missing from a security perspective. Then, instruct them to have a conversation with their agent to try and uncover potential security gaps before they start coding.

**There is no prompt template.** Writing the prompt is part of the exercise. This is intentional — in the real world, developers who think spec-first also have to know what to ask.

If someone is stuck on what to prompt, the minimum nudge is: "Ask your agent to review the requirements as a security reviewer would."

After the agent conversation, they implement based on the enriched specification.

**What to watch for:**
- Does the agent spontaneously mention token expiry? Rate limiting? Enumeration?
- Does the agent catch all six gaps, or only some?
- What does the agent miss entirely?

These observations feed Debrief 2.

---

### Debrief 2 — 5 min

Full group. Ask:

1. "What did your agent flag that you hadn't thought of?"
2. "What did it miss?"
3. "Open `app.py` and `app_2.py` side by side. How different are they?"
4. "What would it take to make this conversation — ask the agent to review the spec before coding — a standard step on your projects?"

The fourth question is the one that matters most. It bridges the exercise back to the session's main theme: the question is not whether to use AI, but *how* to use it deliberately.

If time allows and the conversation is live, you can reveal the six intentional gaps in `requirements.md` and ask which ones their agent caught.

---

## Time management

| Scenario | Adjustment |
|---|---|
| Running 5–10 min behind | Skip Debrief 1. Run both rounds back-to-back, single debrief at the end. |
| Running 10+ min behind | Round 1 becomes a 5-min demo by the presenter. Attendees only do Round 2. |
| Fast finishers | Ask them to add rate limiting to `/reset-password/request`, using the agent to design and implement it. |

---

## What success looks like

The exercise has worked if, during Debrief 2, at least one attendee says something like:

- "My agent caught the expiry thing but I never would have asked without this structure"
- "Round 2 took longer but I'd trust that code more"
- "I could see doing this before every feature ticket, not just in training"

You do not need everyone to have a working implementation. You need everyone to have felt the difference.
