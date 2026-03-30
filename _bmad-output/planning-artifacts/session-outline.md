# Session Outline & Slide Content Guide
### AI in SDLC/SSDLC Workflows — 4-Hour Workshop

> **What this document is:** The complete design blueprint for the workshop. It contains two things:
> 1. The **session agenda** — every block, its timing, type (theory / discussion / hands-on / break), and its role in the flow
> 2. The **slide content guide** — for each slide or slide group, what information and talking points it must contain
>
> **What this document is NOT:** actual slides. This is the content specification that feeds slide creation.

---

## Workshop Purpose & Tone

**Why this is a workshop, not a training:**
The goal is not to teach the full body of knowledge on AI + SSDLC. The goal is to inspire developers to start using AI tools in their secure development workflow. Attendees should leave feeling: "I understand what this looks like in my day-to-day work, I've tried something, and I know where to start."

**The central story arc:**
> "The software developer's job is changing. AI tools are now embedded in every phase of the development lifecycle. The question is not *whether* to use them — it is *which ones*, *how*, and *without breaking security and compliance*. Today you will see it, try it, and figure out where it fits in your world."

**Tone:**
- Collegial, not academic
- Show real things, not concepts only
- Acknowledge skepticism openly
- Create space for debate — split groups, ask questions, let them challenge
- The presenter is a guide, not a lecturer

---

## Narrative Design

### The Five-Act Spine

The workshop follows a single developer journey. The presenter says these transition lines **out loud** at each seam — they are the connective tissue that makes the session feel like a story rather than a sequence of topics.

| Act | Transition Line | Leads Into |
|-----|----------------|------------|
| 1 — Orient | "Before we get to tools — let's make sure we're speaking the same language about AI." | Block 2 |
| 2 — Name the friction | "We know what the landscape looks like. Now — honestly — where does *your* current workflow fall short?" | Block 4 |
| 3 — See the answer | "You named the friction. For the next 30 minutes, I'm going to show you exactly where AI shows up as an answer to what you just described." | Block 5 |
| 4 — Do it yourself | "You've seen it. You've mapped it to your context. Now you're going to do it." | Block 8 |
| 5 — Decide what changes | "You just used it. So — what does that mean for how you work from here?" | Block 9 |

> **Demo realism standard:** All demos and code examples throughout the session must use realistic, consultancy-grade code — real API patterns, real dependency files, real CI configurations. No toy apps, no trivially broken hello-world snippets. Each example should feel like something a developer in the room could have written last week.

---

## Session Agenda

**Total duration:** 4 hours (240 minutes)
**Format:** Workshop — alternates theory blocks, group discussions, live demos, and hands-on

| # | Segment | Type | Duration | Cumulative |
|---|---------|------|----------|------------|
| 1 | Welcome & framing | Theory | 10 min | 0:10 |
| 2 | AI & LLMs: what they actually are | Theory | 20 min | 0:30 |
| 3 | SDLC → SSDLC: the security lens | Theory | 15 min | 0:45 |
| 4 | Pain point discussion — Group work | Discussion | 20 min | 1:05 |
| — | **BREAK** | Break | 10 min | 1:15 |
| 5 | Use cases: AI in real SSDLC workflows | Theory + Demo | 30 min | 1:45 |
| 6 | Use case identification — Group work | Discussion | 15 min | 2:00 |
| 7 | Tools landscape overview | Theory | 25 min | 2:25 |
| — | **BREAK** | Break | 10 min | 2:35 |
| 8 | Hands-on: structured AI-assisted secure dev | Hands-on | 50 min | 3:25 |
| 9 | The job of tomorrow & Monday actions | Theory | 20 min | 3:45 |
| 10 | Q&A | Open | 15 min | 4:00 |

---

## Detailed Block Guide

---

### Block 1 — Welcome & Framing
**Type:** Theory
**Duration:** 10 min
**Role in the session:** Sets the tone, establishes that this is a workshop not a lecture, makes the purpose explicit, and earns attention.

**Slides to cover:**
- Title slide: session name, presenter, date
- "What this session is and what it is not": workshop framing, no exam, bring your skepticism, goal is inspiration
- The central question: "AI is already in your IDE, your CI, your review tools. The question is whether you're driving or just along for the ride."
- Agenda overview (fast — no more than one slide)

**Key talking points:**
- Do not open with definitions. Open with a provocation or a real anecdote.
- Name the elephant: "Some of you may be skeptical. Good. I want you to challenge what you see today."
- Calibrate expectations explicitly: "You won't leave today as an SSDLC expert. You'll leave with one thing you want to try on Monday." Say this out loud — it reduces defensive resistance and reframes the room as participants, not students.
- Be explicit: "We are not here to tell you to use AI blindly. We are here to show you where it fits and where it doesn't."
- Mention that there will be discussion moments — their views matter.

➡️ **Transition:** *"Before we get to tools — let's make sure we're speaking the same language about AI."*

---

### Block 2 — AI & LLMs: What They Actually Are
**Type:** Theory
**Duration:** 20 min
**Role in the session:** Builds a shared, calibrated mental model of AI and LLMs — including the state of the art — before any use case is shown. Prevents both over-hype and under-appreciation.

**Slides to cover:**

**Slide group A — AI landscape (state of the art, 2026)**
- What "AI" means in the developer context today: not robots, not AGI — mostly LLMs and specialized ML models integrated into everyday tooling
- What an LLM is in plain terms: trained on vast text/code, generates probabilistic completions, does not "know" things — it predicts
- The key mental model: *a very fast, very well-read, very confident junior colleague who needs supervision*
- Brief mention of the progression: classic ML models → generative LLMs → LLM-powered tools integrated in IDEs and CI/CD

**Slide group B — AI Agents (state of the art concept)**
Content to include:
- What an AI agent is: an LLM given tools, memory, and the ability to autonomously execute multi-step tasks (browse, write files, run commands, call APIs)
- Examples relevant to development: GitHub Copilot Workspace (plans and executes code changes across a repository), Cursor Agent mode, Devin-style autonomous coding agents
- Why this matters: agents can now run a security scan, read the output, propose fixes, and open a PR — with minimal human prompting
- The governance challenge: the more autonomous the agent, the more important the human review and approval gates become
- Not every team is ready for agents today — but understanding them is table stakes for 2026

**Slide group C — Spec-Driven Development (tease)**
Content to include:
- The problem with vague AI prompts: "write me a login function" produces whatever the model guesses. Insecure by default. Show this on one slide — a real prompt and its subtly insecure output.
- The spec-driven idea in one sentence: write a short specification first — what the code must do, what it must NOT do, which edge cases it must handle, which security constraints apply — then ask AI to implement it
- One concrete hook: "When a developer writes down 'this endpoint must never return data belonging to another user', three things happen: the AI follows the constraint, the reviewer can verify it, and the auditor has evidence it was considered."
- Do not explain the full methodology here. The goal is to make the audience curious. They will see it in action in Use Case 3.

> **Tease line for the presenter:** *"We're going to come back to this in about an hour — and when we do, I think it will change how you think about prompting entirely."*

**Slide group D — What LLMs can and cannot do**
Content to include:
- CAN DO: generate code from description, explain existing code, spot common patterns, suggest fixes, summarize documents, draft specs and documentation, run multi-step agent tasks
- CANNOT DO reliably: reason about novel security threats, guarantee correctness, know your project context, understand client constraints, replace judgment
- The hallucination problem: LLMs produce plausible-sounding wrong answers. This is a security risk, not an inconvenience.

**Slide group E — Confidentiality basics**
Content to include:
- Cloud LLMs (ChatGPT, Copilot, Claude): code you send may be used for training or retained — check terms
- Enterprise/tenant-isolated LLMs: safer, still audit what you allow
- Local LLMs (Ollama, LM Studio): nothing leaves the machine — the answer for restricted client projects
- Rule of thumb: never paste credentials, PII, or proprietary client algorithms into a cloud AI tool

**Key talking points:**
- Use an analogy: "If you hired a contractor who read every Stack Overflow post ever written and every GitHub repo ever published, but who had never shipped a production system — that's an LLM."
- On agents: "An agent is that same contractor, but now with access to your terminal, your files, and your CI pipeline. Useful. Also something you want to supervise."
- Make it concrete: show a real prompt and response, including a wrong or insecure one, to establish healthy skepticism early.
- Do not rush this block. A miscalibrated mental model of AI creates bad habits that last.

> **Presenter time management note:** If you are running behind, cut in this order: (1) trim slide group B (Agents) to definition + one example only; (2) if still behind, reduce slide group C to the problem statement + tease line only — but do not remove it entirely, as it sets up Use Case 3 in Block 5. Slide groups A, D, and E (AI landscape, limitations, confidentiality) are the non-negotiable core of this block — never cut them.

---

### Block 3 — SDLC → SSDLC: The Security Lens
**Type:** Theory
**Duration:** 15 min
**Role in the session:** Fast-establishes shared vocabulary around SDLC, then immediately extends it to SSDLC. The audience knows both concepts; the goal is alignment on terminology and framing, not teaching from scratch.

**Slides to cover:**

**Slide — SDLC at a glance (fast)**
Content to include:
- Classic phases as a visual: Requirements → Design → Implementation → Testing → Deployment → Operations
- One line each: what each phase produces (artifacts, decisions, approvals)
- The modern reality: Agile/DevOps compresses and repeats these phases — the lifecycle is a loop, not a waterfall
- Keep this to one dense slide — the audience already knows this

**Slide — SDLC vs SSDLC side by side**
Content to include:
- Same phases — different activities added at each phase:
  - Requirements: security requirements, authentication/authorization rules, data classification
  - Design: threat modeling, architecture risk review
  - Implementation: secure coding practices, secrets management, dependency hygiene
  - Testing: SAST, SCA, DAST, penetration testing
  - Deployment: secure configuration, environment separation
  - Operations: vulnerability monitoring, incident response, patching
- One sentence: "SSDLC is what happens when you stop treating security as a final gate and start treating it as a design property from day one."

**Slide — The developer's security responsibility**
Content to include:
- In a company with ISO27001 certification, security is not just the CISO's problem
- Annex A has controls directly tied to development: secure coding (A.8.28), security testing (A.8.29), change management (A.8.32) — mention once, do not dwell
- "Security is a quality attribute, like performance. You would not ship code that crashes on every request."

**Slide — The shift-left principle + the AI connection**
Content to include:
- Visual: timeline with security activities moving earlier
- The business case: earlier detection = lower cost, fewer production incidents, fewer audit findings
- The bridge to rest of session: AI tools can automate many of the earlier detection steps — shift-left becomes practical without adding overhead

**Key talking points:**
- Move fast through SDLC — one or two sentences per phase maximum
- Frame SSDLC as "more power, not more burden"

➡️ **Transition:** *"We know what the landscape looks like. Now — honestly — where does your current workflow fall short?"*

---

### Block 4 — Pain Point Discussion (Group Work)
**Type:** Discussion
**Duration:** 20 min
**Role in the session:** Creates identification with the problem space before solutions are presented. Groups articulate what is currently broken or frustrating in their daily security workflow — things like slow code review, unreviewed dependencies, accidental secret commits, no threat modeling, security issues found only in production. This makes the use case demos in Block 5 land as answers to *their* specific problems, not as abstract tool showcases.

**Format:**
- Split into groups of 3–4
- Each group answers 3 questions (displayed on screen):
  1. "In your current projects, where does security feel most painful or neglected?"
  2. "If you could automate one security-related task in your workflow, what would it be?"
  3. "Where does security knowledge come from in your team — a go-to person, a defined process, or whoever happens to care?"
- 12 minutes discussion, 8 minutes brief readout (one sentence per group per question, no synthesis needed yet)

**Facilitator notes:**
- Do not critique or correct answers — collect them
- Note recurring themes on a whiteboard or notepad — they will resurface in Block 5
- Common expected answers: code review is slow, dependency updates are ignored, secrets accidentally committed, no one does threat modeling, tests don't cover security cases
- If a group is stuck: prompt with "What is the last security issue that actually caused you pain on a project?"

➡️ **Transition (after break):** *"You named the friction. For the next 30 minutes, I'm going to show you exactly where AI shows up as an answer to what you just described."*

---

### BREAK — 10 minutes

---

### Block 5 — Use Cases: AI in Real SSDLC Workflows
**Type:** Theory + Live Demo
**Duration:** 30 min
**Role in the session:** The heart of the workshop. Shows — not just tells — how AI fits into the SSDLC. Directly connects to the pain points from Block 4. Creates identification: "I have this exact problem."

> **Note on blocks 5 and 7:** These blocks are intentionally ordered this way. Block 5 shows AI in action through concrete use case stories — each one introduces its tool briefly before demonstrating it, so no prior catalogue knowledge is needed. Block 7 then gives the full tools map, which lands better because attendees already have reference points from the demos. The dependency runs forward, not backward.

> **Running theme for blocks 5, 6, and 7:** Throughout these three blocks, continuously reinforce that AI is genuinely useful across a wide variety of purposes — not just one trick. Each use case, each group discussion moment, and each tool category should leave the audience with a richer picture of the breadth of what AI makes possible in secure development.

**Structure:** 5 use cases, each lasting ~5 minutes. Keep a strict pace — the goal is breadth of recognition, not depth. Each use case follows the same compact pattern:
1. The problem (30 sec)
2. How AI helps (1.5 min)
3. Live or recorded demo (2 min)
4. The human judgment moment — where the developer must still decide (30 sec)

---

**Use Case 1 — AI-assisted secure code review in the IDE**
- Problem: Code review is slow; reviewers miss subtle security issues; juniors don't know what to look for
- AI approach: GitHub Copilot Chat or Copilot Autofix reviews code inline and flags issues with explanations
- Demo: Show a Python or .NET snippet with a subtle injection or secrets handling issue; ask Copilot to review it; show the output
- Human judgment moment: "Copilot flagged 3 things. Is it right? Is the fix correct? Does it fit your codebase?"
- Connect to pain points: tie this directly to what groups said in Block 5 if applicable

---

**Use Case 2 — SAST in CI/CD as a quality gate**
- Problem: Vulnerabilities are often found too late, manually, or not at all
- AI approach: SonarQube (or Semgrep) in the CI pipeline blocks or annotates PRs with AI-generated fix explanations
- Demo: Show a SonarQube dashboard or a PR annotation with a security finding and its explanation
- Human judgment moment: "SonarQube found 12 issues. Which 3 actually matter? How do you suppress false positives with rationale?"
- Tip: emphasize that SonarQube can be self-hosted — relevant for client confidentiality constraints

---

**Use Case 3 — Spec-driven development for security-sensitive features**

[This use case still needs to be brainstormed a bit. Before processing the slides of this use case, ask the user  for brainstorming]

- Problem: AI-generated code from vague prompts is insecure by default — the model fills in security gaps with whatever seems plausible. And when something goes wrong, there is no record of what was intended.
- AI approach: Write a security-aware specification before prompting. The spec defines: what the feature does, what it must NOT do, which edge cases must be handled, which threat vectors were considered, and which security constraints are non-negotiable. Then use AI to implement from the spec — not from a vague description.
- Demo structure (before / after side by side):
  - **Before:** Prompt: *"Write a Python endpoint that returns user profile data."* → AI produces working code, passes basic SAST, but has a missing authorization check — any authenticated user can retrieve any profile by ID. Nothing in the code explains why the check is absent.
  - **After:** Spec (shown on screen, ~10 lines): function purpose, input/output contract, explicit constraint — *"Must verify that the requesting user's ID matches the requested profile ID. Must return 403, not 404, on unauthorized access to avoid enumeration."*, edge cases, known threat: IDOR. → AI implements with the authorization check in place and a comment referencing the spec constraint. The spec is committed alongside the code.
  - Show that the spec is now a reviewable artifact: a reviewer or auditor can read it and verify that the security intent was captured before implementation.
- Human judgment moment: "Is the spec complete? Did it anticipate the right threats? What did AI miss in the implementation that the spec required? Would this spec hold up in a code review or an audit?"
- Connect to ISO27001: the spec is a requirements artifact that directly supports A.8.26 (secure coding practices) and A.8.29 (security testing in development) — intent is documented, not just inferred from code.
- Talking point: "The spec doesn't add overhead. It replaces the time you would have spent re-reviewing AI output that didn't match what you needed. And it leaves a paper trail — which matters when a client asks 'how do you ensure security is considered during development?'"

---

**Use Case 4 — Secret detection and dependency scanning**

[This use case still needs to be brainstormed a bit. Before processing the slides of this use case, ask the user  for brainstorming.]

- Problem: Secrets committed to repos; vulnerable dependencies silently accumulating
- AI approach: GitGuardian pre-commit hooks for secrets; Snyk or OWASP Dependency-Check for dependencies
- Demo: Show a GitGuardian alert on a fake commit with a hardcoded API key; show a Snyk scan of a requirements.txt or .csproj with known CVEs
- Human judgment moment: "Snyk found 47 vulnerable packages. Which ones are actually reachable in my code? Which upgrade breaks my app?"

---

**Use Case 5 — AI-assisted threat modeling (lightweight)**
- Problem: Threat modeling is seen as specialist work; no one does it; design risks are invisible
- AI approach: Structured LLM prompt with architecture description generates STRIDE threat list in minutes
- Demo: Live prompt: "You are a security architect. Here is a data flow for a REST API that handles user authentication and stores PII. Identify STRIDE threats for each component and suggest mitigations." Show output.
- Human judgment moment: "The LLM generated 14 threats. Are any missing? Are any irrelevant to this system? Which 3 do we actually mitigate this sprint?"
- For local/restricted environments: same prompt, run on Ollama locally — demonstrate that it works without internet

---

**Key talking points for the full block:**
- Explicitly reference pain points collected in Block 4 as you go through use cases
- Every use case ends with the human staying in control — this is the recurring message
- Vary the tone: not every demo needs to be a perfect success. Show AI getting something wrong once. It builds trust.
- Keep demos short and real. A live terminal or IDE window beats a polished screenshot.
- Each demo must use realistic consultancy-grade code — see Demo Realism Standard in the Narrative Design section.

---

### Block 6 — Use Case Identification (Group Work)
**Type:** Discussion
**Duration:** 15 min
**Role in the session:** Transfer of ownership — groups connect what they just saw to their real work, and surface practical blockers before the tools overview. Keeps the inspiration momentum from Block 5 alive.

> **Running theme:** Encourage groups to pick *different* use cases from each other, so the readout demonstrates that AI is useful across many different situations, not just one.

**Format:**
- Same groups as Block 4
- Two questions (displayed on screen):
  1. "From what you just saw, pick one use case that maps to a real pain in your current work. Which one and why?"
  2. "What would need to change — in your process, your team, or your tooling — to actually try this approach on your next sprint? Is there a blocker?"
- 8 minutes discussion, 7 minutes readout — one sentence per question per group (keep it tight)

**Facilitator notes:**
- On question 1: prompt stuck groups with "Think about your last sprint — what slowed you down on the security side?"
- On question 2: this surfaces real objections (tool access, client policy, team buy-in) — collect them explicitly, they feed the Tools landscape block and Q&A
- Note responses — they feed the hands-on exercise framing in Block 8

---

### Block 7 — Tools Landscape Overview
**Type:** Theory
**Duration:** 25 min
**Role in the session:** Gives participants a navigable map of what exists. Not a deep dive — a catalogue with enough detail to make informed choices. By this point attendees have seen several tools in action; this block puts them on the map and expands the picture.

> **Running theme:** Use this block to demonstrate that AI's usefulness spreads across every phase and every concern — from writing code to detecting secrets to modeling threats to generating evidence. The breadth of the landscape IS the message: there is an AI tool for almost every pain point in the lifecycle.

**Slides to cover:**

**Slide — The landscape at a glance**
Content: A visual categories map:
- Coding assistants (Copilot, Cursor, Codeium)
- SAST (SonarQube, Semgrep, Snyk Code, Copilot Autofix)
- SCA / Dependencies (Snyk OSS, OWASP Dependency-Check, Dependabot)
- Secret detection (GitGuardian, TruffleHog)
- AI code review (CodeRabbit, Amazon CodeGuru)
- Threat modeling (MS Threat Modeling Tool, OWASP Threat Dragon, LLM prompts)
- Local/offline (Ollama, LM Studio)

**Slide — Picking the right tool: three questions**
Content:
1. Can I use cloud tools on this project, or do I need local/self-hosted?
2. Where in the lifecycle does the pain live — design, coding, testing, review, operations?
3. Does the tool fit my stack (.NET, Python)?

**Slide — The confidentiality decision tree**
Content (simple visual):
- Client project with confidentiality requirements? → Check client AI policy
- Cloud SaaS tool? → Only with explicit approval for that project
- No approval or restricted? → Use Ollama / LM Studio or approved enterprise tool
- Never: credentials, PII, proprietary algorithms in any cloud AI tool

**Slide — The "start here" shortlist for this audience**
Content: A prescriptive shortlist for Python/.NET developers in a consultancy context:
1. **GitHub Copilot** — code assistance; available today, immediate value
2. **SonarQube Community** — SAST; self-hosteable, free, strong .NET and Python coverage
3. **Snyk (free tier) or OWASP Dependency-Check** — dependency scanning; pick based on confidentiality constraints
4. **GitGuardian (free for open source) or TruffleHog** — secret detection
5. **Structured LLM prompting for threat modeling** — zero tooling required, starts immediately

**Slide — What AI does NOT replace**
Content:
- Penetration testing (real attacker creativity)
- Security architecture decisions (context, trade-offs, system knowledge)
- Risk acceptance decisions (business, legal context)
- Compliance interpretation (legal and regulatory judgment)
- Human code review (ownership and accountability)

**Key talking points:**
- "You do not need to adopt everything today. The shortlist is 5 tools/methods. That is a realistic starting point."
- Position the local/offline option as a feature, not a compromise: "Some of your best work may be on the most restricted projects. Ollama means you never have to choose between AI and confidentiality."
- Revisit audience skepticism: "For those who are worried about AI introducing bad code — SonarQube and Snyk are not generative. They detect. They do not write code. Start there."
- Close with a 60-second energizer before the break: "Write down the one tool from today that you want to use during the hands-on. That's what you'll use — bring it loaded and ready after the break."

➡️ **Transition (after break):** *"You've seen it. You've mapped it to your context. Now you're going to do it."*

---

### BREAK — 10 minutes

---

### Block 8 — Hands-On: Vibe Coding vs Spec-Driven Development
**Type:** Hands-on
**Duration:** 50 min
**Role in the session:** The experience that makes the day memorable. Participants feel — not just understand — the difference between unstructured AI prompting and spec-driven development on a real security-sensitive task.

---

#### Setup (5 min)

Attendees clone `quentin-dl-b12/training-ai-ssdlc-exo` (or work from a pre-cloned copy) and open the repo in their IDE.

Four files are relevant:
- `requirements.md` — three user stories describing a password reset feature (read this first)
- `helpers.py` — shared utilities: `DocumentStore`, `send_reset_email`, `logger`. **Do not modify.**
- `app.py` — Round 1 starting file
- `app_2.py` — Round 2 starting file

The existing code already implements `/register` and `/login`. Two endpoint skeletons are waiting to be implemented:
- `POST /reset-password/request` — accepts `{ "email": "..." }`, calls `send_reset_email`, returns a confirmation
- `POST /reset-password/confirm` — accepts `{ "token": "...", "new_password": "..." }`, updates the DB

Both `create_reset_token` and `decode_reset_token` are also left as stubs for attendees to implement.

---

#### Round 1 — Vibe Coding (15 min)

Work in `app.py`. Implement the two endpoints using your AI tool however you like — no rules, no structure. Just get it working.

*Facilitator note: do not give hints. Let people go wherever their instincts take them. The messiness is the point.*

---

#### Debrief 1 (5 min)

Quick show of hands / open question:
- Did your implementation handle the case where the email doesn't exist?
- Did it enforce any limit on how many times a token can be used?
- What does your token contain? Does it expire?

Do not answer these questions yet — hold the tension.

---

#### Round 2 — Spec-Driven (20 min)

Work in `app_2.py`. Before writing any code, open a conversation with your AI agent and ask it to review `requirements.md` and identify what's missing from a security perspective. Use the agent's output to improve the specification, then implement.

No prompt template is provided — writing the prompt is part of the exercise.

*Facilitator note: the requirements are intentionally silent on six OWASP gaps: token TTL, rate limiting, single-use invalidation, audit logging, enumeration protection, token stored as plaintext. A good agent conversation will surface most of these. This will highlight the benefit of agent conversation (spec-driven development) vs pure vibe coding*

---

#### Debrief 2 (5 min)

**Slide: "Does your implementation handle these?"** — display the 6-row reflection table.

Ask participants to self-assess both rounds against the six OWASP gaps that were intentionally omitted from `requirements.md`:

| # | OWASP | Vulnerability |
|---|-------|--------------|
| 1 | A07 | Token TTL — does the reset token expire? |
| 2 | A07 | Single-use invalidation — is the token voided after use? |
| 3 | A04 | Rate limiting on `/reset-password/request` |
| 4 | A01 | Email enumeration — does the endpoint leak whether an email exists? |
| 5 | A09 | Audit logging for reset requests and confirmations |
| 6 | A02 | Token storage — plaintext vs hashed |

Full group discussion:
- Which gaps did Round 1 miss that Round 2 caught?
- Which did your agent miss even in Round 2?
- What would it take to make this checklist part of every feature's definition-of-done?

---

#### Time management
- If short on time: skip Debrief 1, run both rounds back-to-back and debrief once at the end
- Fast finishers: add rate limiting to `/reset-password/request` (ask the agent how)

➡️ **Transition:** *"You just used it. So — what does that mean for how you work from here?"*

---

### Block 9 — The Job of Tomorrow & Monday Actions
**Type:** Theory
**Duration:** 20 min
**Role in the session:** Elevates the conversation from tools to identity, then closes with concrete actions. Moves from "what does this mean for your career?" directly to "what do you do on Monday?" — keeping the close tight and actionable.

**Slides to cover:**

**Slide — What consultancy developers gain specifically** *(open with this)*
Content:
- Portable practices: the AI-enhanced SSDLC habits you build work on any client project
- Evidence generation: AI-assisted documentation and review trails help meet client compliance demands
- Competitive differentiation: teams that deliver secure software faster win more engagements

**Slide — The new developer skill profile**
Content (the skills that gain importance):
- Prompt engineering as a professional skill: writing specifications and structured prompts that produce reliable, verifiable outputs
- Security reasoning: understanding what AI cannot catch, and applying judgment where AI fails
- Evidence and traceability: structuring work so AI-assisted outputs are auditable and defensible
- Tool evaluation: knowing which tools fit which constraints and how to compare them

Content (the skills that remain irreplaceable):
- System understanding and architecture reasoning
- Client and business context judgment
- Accountability — AI does not sign off on code. Developers do.

**Slide — The risk of not engaging**
Content:
- Teams that do not adopt structured AI workflows will see others deliver faster and with fewer security defects
- Ungoverned AI adoption (vibe coding, raw prompts, no verification) creates new risks: insecure AI-generated code, compliance gaps, confidentiality leakage
- The sweet spot: governed, structured, human-reviewed AI use — which is exactly what this workshop has been about

**Slide — Your Monday shortlist**
Content:
1. Install GitHub Copilot (or enable Ollama if confidentiality is a concern) and use it on a real task — then review everything it suggests before committing
2. Run OWASP Dependency-Check or Snyk on one project you are currently working on
3. Next time you start a security-sensitive feature: write a one-page spec including the security requirements before touching the code
4. Identify one place in your team's CI/CD pipeline where a security gate is missing or disabled
5. In your next code review, ask: "What would an attacker do with this code?" — even without a tool

**Slide — Resources to explore**
Content:
- OWASP Top 10 (developer-facing security reference)
- SonarQube Community (free, self-hosted SAST)
- Ollama (local LLM — ollama.com)
- GitHub Copilot free tier
- OWASP Dependency-Check
- GitGuardian free tier
- Semgrep OSS

**Slide — The one thing to remember**
Content: One sentence, large on screen:
> "AI is a powerful junior colleague. Supervise it, structure your requests, verify its output, and keep the accountability where it belongs — with you."

**Key talking points:**
- Open with the consultancy business case — make it personal and concrete before going abstract
- Keep this hopeful and honest, not evangelical
- Acknowledge that figuring out the right boundaries is itself a professional skill that takes time to develop
- Bridge identity to action explicitly: "So — concretely — what do you take from today and apply on Monday?"
- Do not add more items to the Monday list during Q&A. Protect the simplicity.
- Reiterate: "You do not have to implement everything. Pick one thing that connects to a real pain in your current project."

➡️ **Transition:** *"That is a wrap. Before we close — questions, challenges, pushback. This is the time."*

---

### Block 10 — Q&A
**Type:** Open
**Duration:** 15 min

**Facilitator notes:**
- Expect challenges from senior developers: "What about confidentiality on client X?" / "We tried Copilot and it gave us terrible code" / "ISO27001 does not require this"
- Prepare responses for common objections:
  - Confidentiality: Ollama is the answer. Self-hosted SonarQube is the answer.
  - Bad AI output: Exactly why you verify and why spec-first matters
  - ISO27001: It does not prohibit AI. A.8.28 says secure coding practices must exist and be followed — AI-assisted coding is still subject to those practices.
- If the session ran short and time allows: invite one group to share their Block 6 use case identification with the full room

---

## Notes for Slide Production

**Format:** One Markdown file per slide, organized in folders by block.

**File structure:** `_bmad-output/slides/block-NN-name/NN-slide-name.md`

**Authoring guidelines:**
- One idea per slide — resist putting everything on one slide
- Use bullet points, enumerations, tables, and code blocks over prose
- Target ~70 words per slide (guideline, not a hard limit — complex slides may exceed this)
- Live demo slides use a clear `🔴 LIVE DEMO` marker — no content needed, just the demo context
- Group discussion slides display the question(s) clearly and include a readout timing note
- Presenter notes are in this outline document, not in the slide files

**Slide count:** ~52 slides across 10 blocks

**Language:** English throughout

---

*Document prepared for training design purposes — March 2026*
