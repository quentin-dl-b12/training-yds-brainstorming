# Run-of-the-Show
### "AI in SDLC/SSDLC Workflows" — 4-Hour Workshop

> **What this document is:** Your 15-minute brief before you walk in the room. It covers the session's purpose, the narrative arc, the common thread to repeat throughout, and a per-block cheat sheet. Use it as a last-minute anchor — not a script.
> **Estimated reading time:** ~15 minutes.

---

## The Workshop in 30 Seconds

**Who:** Python/.NET developers at a Tunisia-based consultancy. Mixed seniority. Expect healthy skepticism toward AI.

**What:** A 4-hour workshop that shows AI in action across the SSDLC, then gives participants a hands-on moment to feel the difference between unstructured prompting and spec-driven development.

**Goal:** Attendees leave with **one concrete thing they want to try tomorrow** — not expertise, not a toolkit, just a first step lowered enough that they'll take it.

**Tone:** Collegial, not academic. Guide, not lecturer. Show real things. Acknowledge skepticism openly — it's not resistance, it's quality control.

---

## The Narrative Arc — Five Acts

The session follows a single developer journey. Say these transitions **out loud** at each seam — they are the connective tissue that prevents the session from feeling like a sequence of slides.

| Act | What you're doing to the room | Transition line to say out loud |
|---|---|---|
| **1 — Orient** | Calibrate expectations. Earn attention. | *"Before we get to tools — let's make sure we're speaking the same language about AI."* |
| **2 — Name the friction** | Surface what's broken in their world before showing the answer. | *"We know what the landscape looks like. Now — honestly — where does your current workflow fall short?"* |
| **3 — See the answer** | Show AI as a direct response to the friction they named. | *"You named the friction. For the next 30 minutes, I'm going to show you exactly where AI shows up as an answer to what you just described."* |
| **4 — Do it yourself** | Make the difference visceral, not just conceptual. | *"You've seen it. You've mapped it to your context. Now you're going to do it."* |
| **5 — Decide what changes** | Elevate from tools to identity. Close with action. | *"You just used it. So — what does that mean for how you work from here?"* |

**The emotional arc you're managing:**
Skepticism → Curiosity → Recognition → Experience → Ownership

---

## The Common Thread

### Internal compass (what you carry in your head throughout)

> **"You have the judgment. AI gives you leverage."**

This is the session's spine. Every demo, every discussion, every exercise is an instance of it. The developer's expertise is not being replaced — it is being amplified.

### Spoken anchor (what you say out loud at recurring moments)

At every **"human judgment moment"** in the demos (Block 5), and at the key inflection points in Block 8, drop this line:

> *"Here's where you stay in the driver's seat — the model can't make this call."*

This combines both registers:
- It addresses the developer directly (*"you stay in the driver's seat"*)
- It names the limitation of AI explicitly (*"the model can't make this call"*)

Say it **every time** — it is the repetition that makes it feel woven in rather than tacked on. By Block 8, participants will anticipate it. That's the goal.

### How the thread evolves across the session

| Act | How it manifests |
|---|---|
| Block 1 | Promise: *"We're not here to tell you to use AI blindly. We're here to show you where it fits — and where it doesn't."* |
| Block 2 | Context: *"The model predicts. It doesn't know. Supervise it."* |
| Block 5 | Evidence: close every demo with the spoken anchor |
| Block 8 | Experience: *"Your judgment shaped what you asked the agent. AI gave you the leverage to find what the requirements were missing."* |
| Block 9 | Identity: *"The skills that matter most are the ones that stay yours: judgment, context, accountability."* |

---

## Block-by-Block Cheat Sheet

---

### Block 1 — Welcome & Framing
⏱️ **10 min** | Cumulative: 0:10 | Type: Theory

🎯 **Objective:** Set the room as a workshop (not a lecture). Earn attention. Calibrate expectations explicitly.

💬 **How to open:** Don't start with the agenda slide. Open with a provocation or a real anecdote — something that makes someone in the room say "yes, that happens to me." *Then* say: *"You won't leave today as an SSDLC expert. You'll leave with one thing you want to try on Monday."* Say this aloud — it reduces defensive posture immediately.

🔄 **Common thread moment:** *"We are not here to tell you to use AI blindly. We are here to show you where it fits and where it doesn't."*

⚠️ **Trap to avoid:** Opening with definitions. Starting any sentence with "Today we will cover..." Name the elephant instead: *"Some of you may be skeptical. Good. I want you to challenge what you see today."*

⚡ **Transition out:** *"Before we get to tools — let's make sure we're speaking the same language about AI."*

---

### Block 2 — AI & LLMs: What They Actually Are
⏱️ **20 min** | Cumulative: 0:30 | Type: Theory

🎯 **Objective:** Build a calibrated mental model of AI — neither hype nor dismissal. This block prevents bad habits that form from misconceptions.

💬 **How to open:** Lead with the analogy: *"If you hired a contractor who read every Stack Overflow post and every GitHub repo ever published — but had never shipped a production system — that's an LLM."*

🔄 **Common thread moment:** Slide group C (spec-driven tease) — *"We're going to come back to this in about an hour — and when we do, I think it will change how you think about prompting entirely."* Don't explain yet. Just seed the curiosity.

⚠️ **Trap to avoid:** Rushing this block. A miscalibrated mental model creates bad habits that last the whole session. Also: do not skip the hallucination slide — it sets the right level of healthy skepticism.

📋 **Cut guide (if running behind):**
- Trim first: Slide group B (agents) → definition + one example only
- Trim second: Slide group C → problem statement + tease line only
- **Never cut:** Slide groups A (AI landscape), D (limits), E (confidentiality)

⚡ **Transition out:** [leads into Block 3 — no explicit transition line]

---

### Block 3 — SDLC → SSDLC: The Security Lens
⏱️ **15 min** | Cumulative: 0:45 | Type: Theory

🎯 **Objective:** Align vocabulary on SDLC and SSDLC. Frame security as a quality attribute, not a compliance burden.

💬 **How to open:** Move fast through the SDLC phases slide — one sentence per phase maximum. The audience knows this.

🔄 **Common thread moment:** The shift-left + AI connection slide — *"AI tools can automate many of the earlier detection steps — shift-left becomes practical without adding overhead."* This is the first concrete bridge between SSDLC and AI tools.

⚠️ **Trap to avoid:** Dwelling on ISO27001 detail. Name the developer-facing controls once (A.8.28, A.8.29, A.8.32), don't lecture. If someone asks a deep compliance question, redirect: *"That's exactly the territory Block 7 covers — let's get there."*

⚡ **Transition out:** *"We know what the landscape looks like. Now — honestly — where does your current workflow fall short?"*

---

### Block 4 — Pain Point Discussion
⏱️ **20 min** | Cumulative: 1:05 | Type: Group Discussion

🎯 **Objective:** Surface real friction in participants' workflows. Prime Block 5 to land as answers to *their* problems — not abstract demos.

💬 **How to open:** Split into groups of 3–4. Display three questions. Give 12 minutes for discussion, 8 for readout.

🔄 **Common thread moment:** None during the discussion itself — but write down the recurring pain points on a whiteboard or notepad. You will call them back explicitly in Block 5.

⚠️ **Trap to avoid:** Correcting or synthesizing answers during the readout. Just collect. If a group is stuck, prompt with: *"What's the last security issue that actually caused you pain on a project?"*

⚡ **Transition out:** *[After break]* *"You named the friction. For the next 30 minutes, I'm going to show you exactly where AI shows up as an answer to what you just described."*

---

### 🔶 BREAK — 10 min | Cumulative: 1:15

---

### Block 5 — Use Cases: AI in Real SSDLC Workflows
⏱️ **30 min** | Cumulative: 1:45 | Type: Theory + Live Demo

🎯 **Objective:** Show — not tell — AI in the SSDLC. Create "I have this exact problem" recognition for as many participants as possible.

💬 **How to open:** Explicitly reference two or three pain points collected in Block 4. *"You mentioned [X]. Use Case 1 is exactly that."*

🔄 **Common thread moment (critical — repeat at every demo):** Close every use case demo with: *"Here's where you stay in the driver's seat — the model can't make this call."* This is meant to be said at the "human judgment moment" of every use case. Five use cases = five instances of the spoken anchor. The repetition is intentional.

**Structure per use case (5 min each):**
| Step | Duration |
|---|---|
| The problem (30 sec) | Name the pain. Connect to Block 4 if applicable. |
| How AI helps (90 sec) | The approach and the tool — brief. |
| Live or recorded demo (2 min) | Keep it real. A live terminal beats a screenshot. |
| Human judgment moment (30 sec) | Drop the spoken anchor. |

**The 5 use cases:**
1. AI-assisted secure code review in the IDE (GitHub Copilot Chat)
2. SAST in CI/CD as a quality gate (SonarQube / Semgrep)
3. Spec-driven development for security-sensitive features (before/after side-by-side)
4. Secret detection and dependency scanning (GitGuardian + Snyk)
5. AI-assisted threat modeling — lightweight STRIDE prompt (Ollama option for restricted envs)

⚠️ **Trap to avoid:** Letting one demo run long and cutting another. Skipping the human judgment moment to save time — that's the thread, never drop it. Also: show AI getting something wrong at least once — it builds trust.

⚡ **Transition out:** [leads into Block 6 — no explicit transition line]

---

### Block 6 — Use Case Identification
⏱️ **15 min** | Cumulative: 2:00 | Type: Group Discussion

🎯 **Objective:** Transfer ownership. Groups connect what they saw to their real work and surface practical blockers.

💬 **How to open:** Same groups as Block 4. Two questions on screen. 8 min discussion, 7 min tight readout.

🔄 **Common thread moment:** Question 2 asks about blockers (tool access, client policy, team buy-in). Collect them explicitly — *"I'm hearing 'client policy' come up more than once. We'll cover the confidentiality decision tree in Block 7."*

⚠️ **Trap to avoid:** Groups all picking the same use case. Encourage diversity: *"For the readout, let's hear a different use case from each group."* This demonstrates that AI is useful across many situations — that breadth is itself a message.

⚡ **Transition out:** [leads into Block 7 — no explicit transition line]

---

### Block 7 — Tools Landscape Overview
⏱️ **25 min** | Cumulative: 2:25 | Type: Theory

🎯 **Objective:** Give a navigable map of the tool ecosystem. Breadth over depth — this is a catalogue, not a tutorial.

💬 **How to open:** *"You do not need to adopt everything today. The shortlist is 5 tools. That is a realistic starting point."*

🔄 **Common thread moment:** On the "start here" shortlist slide — *"Each of these gives you leverage on a pain point you named today."* On the confidentiality decision tree — *"And for those of you on restricted projects: Ollama means you never have to choose between AI and client confidentiality."*

**The shortlist to know (5 starting points for this audience):**
1. **GitHub Copilot** — code assistance; available immediately
2. **SonarQube Community** — self-hosted SAST; free, .NET + Python coverage
3. **Snyk (free) or OWASP Dependency-Check** — dependency scanning
4. **GitGuardian or TruffleHog** — secret detection
5. **Structured LLM prompting** — threat modeling, zero setup required

⚠️ **Trap to avoid:** Going deep on any single tool. If someone asks a detailed technical question: *"Let's park that for Q&A — we want to cover the full map first."*

⚡ **Transition out:** 60-second energizer before the break — *"Before you stand up: make sure your IDE is open and your AI assistant is ready. We're going to write code after the break — you want zero friction when we start."* Then: *[after break]* *"You've seen it. You've mapped it to your context. Now you're going to do it."*

---

### 🔶 BREAK — 10 min | Cumulative: 2:35

---

### Block 8 — Hands-On: Vibe Coding vs. Spec-Driven Development
⏱️ **50 min** | Cumulative: 3:25 | Type: Hands-On

🎯 **Objective:** Make the difference between unstructured AI prompting and spec-driven development *felt*, not just understood.

💬 **How to open:** *"This is a real FastAPI application. /register and /login already work. Your job is to implement password reset. You have the user stories. You have the helper utilities. The rest is up to you and your AI tool."* Take questions about tech stack only. Do not answer questions about what the implementation should look like.

**The structure:**

| Phase | Duration | What you do |
|---|---|---|
| **Setup** | 5 min | Everyone opens the repo; reads README and `requirements.md` |
| **Round 1 — Vibe Coding** (`app.py`) | 15 min | No rules, no structure. Walk the room. Stay silent on security. Note interesting approaches. |
| **Debrief 1** | 5 min | Ask three questions — hold the tension, do not resolve it yet |
| **Round 2 — Spec-Driven** (`app_2.py`) | 20 min | Before writing a line, participants have an agent conversation to find what `requirements.md` is *not* saying |
| **Debrief 2** | 5 min | Display the 6-gap table; full group reflection |

**Debrief 1 — three questions to ask (hold the tension):**
1. *"Did your implementation handle the case where the email doesn't exist? What does it return?"*
2. *"Can the same reset token be used twice? Three times?"*
3. *"What's inside your JWT? Does it expire?"*

> Do not answer these yet. The point is to make people curious, not to make them feel corrected.

**Round 2 nudge (if someone is stuck on what to prompt):** Minimum nudge only — *"Ask your agent to review the requirements as a security reviewer would."*

**Debrief 2 — the 6 intentional gaps in `requirements.md`:**

| # | OWASP | What was missing |
|---|---|---|
| 1 | A07 | Token expiry (TTL) |
| 2 | A07 | Single-use invalidation |
| 3 | A04 | Rate limiting on `/reset-password/request` |
| 4 | A07 | Enumeration protection (does endpoint reveal whether email exists?) |
| 5 | A09 | Audit logging for reset attempts |
| 6 | A02 | Token stored as plaintext in the database |

🔄 **Common thread moment (Debrief 2):** *"Your judgment shaped what you asked the agent. AI gave you the leverage to find what the requirements were missing. That's the difference between vibe coding and spec-driven development — and it's replicable on every project."*

⚠️ **Trap to avoid:** Giving security hints during Round 1. Answering "should I validate the token?" with anything other than "What do you think the requirements say?" Also: the goal is not a finished, working implementation — it is the awareness of what was missed.

📋 **Cut guide (if running behind):**
- Skip Debrief 1 → run both rounds back-to-back, single debrief at end
- If very short: Round 1 becomes a 5-min presenter demo; participants only do Round 2

⚡ **Transition out:** *"You just used it. So — what does that mean for how you work from here?"*

---

### Block 9 — The Job of Tomorrow & Monday Actions
⏱️ **20 min** | Cumulative: 3:45 | Type: Theory

🎯 **Objective:** Elevate from tools to identity. Close with five concrete actions that feel achievable before the weekend is over.

💬 **How to open:** Lead with the consultancy business case — *"Portable practices. Evidence generation. Competitive differentiation. These aren't abstract benefits — they show up in how fast you deliver and how well your work holds up under a client audit."*

🔄 **Common thread moment (final instance):** On the "new developer skill profile" slide — *"The skills that gain importance are all about how you direct AI. The skills that stay irreplaceable are all about judgment and accountability. You have the judgment. AI gives you leverage."*

⚠️ **Trap to avoid:** Adding items to the Monday shortlist during discussion. Protect its simplicity — maximum 5 items, no exceptions. *"Pick one thing that connects to a real pain in your current project."*

**The Monday shortlist (protect these 5 — do not grow the list):**
1. Install GitHub Copilot (or enable Ollama) — use it on a real task — review everything before committing
2. Run OWASP Dependency-Check or Snyk on one project you're currently working on
3. Next time you start a security-sensitive feature: write a one-page spec with security requirements *before* touching the code
4. Find one place in your CI/CD pipeline where a security gate is missing or disabled
5. In your next code review, ask: *"What would an attacker do with this code?"* — even without a tool

⚡ **Transition out:** *"That is a wrap. Before we close — questions, challenges, pushback. This is the time."*

---

### Block 10 (Block 11 in slides) — Q&A
⏱️ **15 min** | Cumulative: 4:00 | Type: Open

🎯 **Objective:** Surface and address remaining skepticism. Land the session cleanly.

💬 **How to open:** Invite challenges openly — *"Questions, challenges, pushback — all welcome."*

🔄 **Common thread moment (final close):** Land the session with the closing quote from the slides: *"AI is a powerful junior colleague. Supervise it, structure your requests, verify its output, and keep the accountability where it belongs — with you."*

⚠️ **Trap to avoid:** Introducing new content. This is a landing pad. Also: do not try to fill silence — let questions come.

**Likely pushback and responses:**

| Objection | Response |
|---|---|
| *"What about confidentiality on client X?"* | "Ollama for local LLMs, self-hosted SonarQube. Neither sends data anywhere. That's exactly why they're on the shortlist." |
| *"We tried Copilot and it gave us terrible code"* | "Yes — which is why spec-first matters. Vague prompt = whatever the model guesses. Structured prompt + verification = a different experience. That's what today was about." |
| *"ISO27001 doesn't require any of this"* | "It doesn't prohibit AI either. A.8.28 requires secure coding practices to be followed. AI-assisted coding is still subject to those practices. What we showed today is how to meet them more consistently." |
| *"AI will hallucinate security issues that aren't there"* | "Agreed — which is why we closed every demo with a human judgment moment. The model surfaces candidates. You decide. That's the model." |

---

## Hands-On Exercise — Quick Reference

> ⚠️ The full facilitator guide is a separate document (`exercise-guide.md`). Read it in full before the session. This is a 2-minute reminder only.

**Repo:** `quentin-dl-b12/yds-training-exercises` (Python version in root)

**Four files:**
- `requirements.md` — three user stories for password reset. Read-only.
- `helpers.py` — `DocumentStore`, `send_reset_email`, `logger`. Do not modify.
- `app.py` — Round 1 (vibe coding)
- `app_2.py` — Round 2 (spec-driven)

**Already implemented:** `/register` and `/login`

**Left for participants to implement:** `POST /reset-password/request`, `POST /reset-password/confirm`, `create_reset_token(email)`, `decode_reset_token(token)`

**The exercise works if:** someone says *"I could see doing this before every feature ticket"* — not if everyone has a working implementation.

---

*Prepared for the "AI in SDLC/SSDLC Workflows" workshop — March 2026*
