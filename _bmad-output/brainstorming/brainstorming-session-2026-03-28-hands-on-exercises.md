---
stepsCompleted: [1, 2]
session_topic: 'Redesigning Block 8 hands-on around vibe coding vs spec-driven development using BMAD method'
session_goals: 'Design a 50-min hands-on exercise that creates a direct, felt contrast between vibe coding and BMAD-driven spec development on a security-sensitive feature; reveal unnoticed vulnerabilities through agent conversation'
selected_approach: 'Concept defined — moving to design refinement'
techniques_used: ['Reverse Brainstorming (partial)', 'Direct concept definition by Quentin']
context_file: '_bmad-output/planning-artifacts/session-outline.md'
---

# Brainstorming Session — Block 8 Hands-On Exercises (v2)

**Date:** 2026-03-28

---

## Session Context

- **Workshop:** AI in SDLC/SSDLC Workflows — 4-hour workshop
- **Block 8:** 50-min hands-on
- **Exercise repo:** `quentin-dl-b12/training-ai-ssdlc-exo` (Python + .NET versions)
- **Audience:** Mixed junior/senior developers, Tunisia-based consultancy, ISO27001-certified

---

## Core Exercise Concept (Defined by Quentin)

### The Setup
Attendees start from:
- A **blank page** (or already-implemented helper functions as scaffolding)
- A **Markdown requirements file** (user stories) that *looks* complete — mentions some security requirements — but **intentionally omits** several key vulnerabilities inspired by OWASP Top 10

The omissions are the trap. The exercise is about discovering them.

### Round 1 — Vibe Coding
- Attendee implements the feature from the requirements using their AI tool, prompting naturally
- No structure, no spec — just "here are the requirements, build it"
- Expected outcome: working code that satisfies the stated requirements but contains natural, unnoticed vulnerabilities corresponding to the intentional omissions

### Round 2 — BMAD Spec-Driven
- Start from a **duplicate of the same context** (same requirements file, blank implementation)
- Use BMAD-style agent conversation to **brainstorm vulnerabilities *before* jumping to implementation**
- The agent dialogue surfaces security issues that the requirements didn't capture
- Then implement from the enriched spec

### Success Criterion
**Not** a finished implementation. **Not** bug-free code.

> Success = the attendee realizes that structured agent conversation revealed security issues they completely missed during vibe coding or would have missed during manual implementation.

### BMAD's Role
BMAD is the spec-driven tool. Its structured agent prompting methodology is what creates the security-focused brainstorming conversation before implementation begins.

---

## Intentional Omissions — OWASP Top 10 Inspiration

Vulnerabilities to *not mention* in the requirements doc, so attendees must discover them through agent conversation:

| OWASP Category | Omitted vulnerability example |
|---------------|-------------------------------|
| A01 — Broken Access Control | No mention of authorization checks (e.g., IDOR — any user can access any resource by ID) |
| A03 — Injection | No mention of input sanitization / SQL injection prevention |
| A07 — Auth Failures | No mention of session expiry, token invalidation, or brute-force protection |
| A04 — Insecure Design | No mention of rate limiting on sensitive endpoints |
| A09 — Logging Failures | No mention of audit logging for sensitive operations |
| A02 — Cryptographic Failures | No mention of encryption for sensitive fields at rest |

*Note: the requirements doc should mention 1–2 security requirements (e.g., "authentication is required") to look credible — but leave the above gaps unaddressed.*

---

## Decisions Locked (2026-03-28) — Updated

| Decision | Choice |
|----------|--------|
| Feature | Password reset API (Python / FastAPI) |
| Requirements doc | Standalone `requirements.md` — actual Markdown file, shared between both rounds. Length: as many lines as needed, no artificial limit. Must provide sufficient context without leaking security requirements. |
| Reset route skeleton | Function signature + `...` only. No docstring, no DB call, no hints. |
| Scaffolding (separate `helpers.py`) | Document store class, `send_reset_email()` mock, logging setup, JWT helpers (see below). Login + register routes stay in `app.py`. |
| DB mock | Document store class with private `dict` attribute as backing store. Keys = document IDs, values = dicts (e.g. `{"email": ..., "password_hash": ..., "reset_token": ...}`). |
| Email mock | Public function `send_reset_email(address: str, token: str)` — docstring describing intent, `raise NotImplementedError`. |
| Logging | `logging.getLogger(__name__)` pre-configured, ready to use with no setup needed. |
| Repo structure | Two copies of the API route file: `round1_vibe/app.py` and `round2_spec/app.py`. Helpers and requirements shared. See structure below. |
| Exercise instructions | On slides — not in written documents. Keeps the room focused on the screen, not their laptop. |
| BMAD prompt card | **No pre-written prompts.** Attendees write their own prompts in Round 2. The point of the exercise is to get them to formulate the right questions themselves. The slide instruction gives minimal framing only: "have a conversation with your agent about what's missing before you write any code." |
| Debrief Q1 (revised) | Open, non-assuming: *"What security requirements did you handle in Round 1 — whether from the spec or from your own instinct?"* Acknowledges that seniors will have spotted obvious ones. |

---

## JWT Helper Functions — Decision

**Recommendation: provide helpers. Reason:**

FastAPI + JWT from scratch in 12 minutes risks derailing Round 1 into library setup. Providing `create_reset_token(email)` and `decode_reset_token(token)` as helpers means the *mechanism* works — but the *security gaps* in how tokens are used (no expiry enforced at the route level, token not invalidated after use, token stored plaintext) remain for attendees to discover.

**Proposed helpers in `helpers.py`:**
- `create_reset_token(email: str) -> str` — creates a signed JWT. Intentional gap: no TTL set (or TTL set to a very long value), attendees must notice.
- `decode_reset_token(token: str) -> str` — decodes and returns email. Intentional gap: does not check if token has already been used.

This keeps JWT as a vulnerability surface, not a setup burden.

---

## Repository Structure (Final)

```
training-ai-ssdlc-exo/
├── README.md          ← setup instructions only (Python version, pip install, how to run)
├── requirements.md    ← shared user stories (intentionally incomplete)
├── helpers.py         ← DB mock, email mock, logging, JWT helpers
├── app.py             ← Round 1 (vibe coding) — comment at top of file
└── app_2.py           ← Round 2 (spec-driven) — identical copy, comment at top of file
```

*Note: `app.py` and `app_2.py` are identical at exercise start. Attendees should not modify `helpers.py` or `requirements.md`. The README contains no mention of vulnerabilities or exercise objectives — setup only.*

**Top-of-file comments:**
- `app.py`: `# ROUND 1 — Vibe coding. Implement POST /reset-password using your AI tool however you like.`
- `app_2.py`: `# ROUND 2 — Spec-driven. Before writing any code, have a conversation with your agent about what's missing from the requirements.`

---

## Exercise Flow (Slide-Driven)

Slides deliver all instructions. No written exercise document.

| Slide | Content |
|-------|---------|
| 1 | "Open the repo. Read `requirements.md`. Open `round1_vibe/app.py`." |
| 2 | "Round 1 — Use your AI tool however you want. Implement `POST /reset-password`. **Do not modify existing routes.** 12 minutes." |
| 3 | *(Pivot moment)* "Stop. Look at what you built. What did you handle? What did you assume?" — 3 min silent reflection |
| 4 | "Round 2 — Open `round2_spec/app.py`. Before writing any code, have a conversation with your agent: ask it what's missing from the requirements. Then implement from what you learned. 20 minutes." |
| 5 | Debrief questions (oral) |

---

## Debrief Questions (Oral, Presenter-Led)

1. *"What security requirements did you handle in Round 1 — whether from the spec or from your own instinct?"*
2. *"What did the agent surface in Round 2 that you hadn't thought of?"*
3. *"If you shipped Round 1's implementation to a client today, what would keep you up at night?"*

---

## Open Design Questions (Remaining)

1. **`requirements.md` content** — Draft needed. User stories for password reset, credible security mentions (auth required, token-based link), silence on all 6 omissions.
2. **`helpers.py` content** — Draft needed. Document store, email mock, logger, JWT helpers with intentional gaps.
3. **`app.py` content** — Draft needed. `/login` + `/register` with natural vulnerabilities, imports from `helpers.py`, reset skeleton.

---

## BMAD in This Context — Explanation for Quentin

BMAD is a structured AI agent methodology. In normal use it has many phases (analysis, architecture, stories, implementation). For this exercise we don't use the full framework — we use a **simplified single-agent conversation** that replicates the most valuable part: **security-focused brainstorming before writing any code**.

### What it looks like in practice

Instead of prompting: *"Implement a password reset endpoint"* —

The attendee opens a conversation with their AI tool and runs a structured role-play in two steps:

**Step 1 — Security analyst role:**
> "You are a security analyst reviewing requirements for a password reset API. Here are the user stories: [paste requirements doc]. Before any implementation begins, what security concerns, edge cases, and threat vectors are NOT addressed in these requirements? Be exhaustive."

The agent responds with a list of gaps — SQL injection risk, missing rate limiting, token expiry not mentioned, no audit log, etc.

**Step 2 — Spec enrichment:**
> "Based on those concerns, write a security-enriched specification for the password reset endpoint. For each requirement you add, explain which OWASP category it addresses."

The agent produces an enriched spec. **Then** the attendee implements from that spec, not from the original requirements.

### Why this is "BMAD-lite"

BMAD's core insight is: *talk to agents in structured roles before building*. The full framework has PM agents, architect agents, story agents, etc. For this exercise we collapse that into one analyst conversation — but the principle is identical. Attendees don't need to know what BMAD is. They just need a **prompt card** with the two steps above, pre-filled with everything except the requirements paste.

### What makes this work vs. vibe coding

- **Vibe coding:** attendee implements directly → satisfies stated requirements → misses unstated vulnerabilities
- **BMAD-lite:** attendee forces a conversation about what's *missing* → surfaces OWASP gaps → implements from enriched spec
- The gap between the two rounds is the lesson

---
