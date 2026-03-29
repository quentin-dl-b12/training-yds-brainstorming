# AI Tools & Methodologies Catalogue
### For AI-Enhanced SSDLC and ISO27001 Compliance Training

> **Purpose:** A structured reference of AI tools and methodologies that can be integrated into secure software delivery workflows. Each entry includes what the tool does, where it fits in SSDLC, its compliance relevance, confidentiality posture, and training suitability.

---

## How to Read This Catalogue

Each tool is tagged with:
- **SSDLC Phase** — where in the lifecycle it applies
- **ISO27001 Controls** — which Annex A controls it supports
- **Tool Type** — what category of work it performs
- **Confidentiality Posture** — cloud SaaS / enterprise / local/offline
- **Training Suitability** — how suitable for live demo or exercise in this training

---

## Category 1 — AI-Assisted SAST (Static Application Security Testing)

### SonarQube (Community / Developer / Enterprise)
- **Tool Type:** SAST + code quality
- **SSDLC Phase:** Implementation, Testing, CI/CD gate
- **ISO27001 Controls:** A.8.28 Secure coding, A.8.29 Security testing, A.8.32 Change management
- **Confidentiality Posture:** Self-hosted (Community/Enterprise) or SonarCloud (SaaS)
- **Languages:** Python, C#/.NET, Java, JS, and many more
- **What it does:** Analyzes source code for security vulnerabilities (injection, XSS, hardcoded credentials, insecure deserialization, etc.), code smells, and maintainability issues. Enterprise tier adds AI-powered suggestions and fix explanations.
- **AI angle:** AI-generated remediation explanations, "Clean as You Code" approach, PR decoration in CI/CD, issue prioritization
- **Strengths:** Excellent .NET and Python coverage; widely used in enterprise; integrates with GitHub, GitLab, Azure DevOps; can be self-hosted for confidentiality
- **Limitations:** Can produce false positives; requires triage discipline; AI fix suggestions still need human validation
- **Training suitability:** ⭐⭐⭐⭐⭐ — ideal for live demo, well-known brand, real output easy to interpret

---

### Semgrep (OSS / Semgrep Pro)
- **Tool Type:** SAST + custom rule engine
- **SSDLC Phase:** Implementation, Testing, CI/CD gate
- **ISO27001 Controls:** A.8.28, A.8.29
- **Confidentiality Posture:** Self-hosted OSS version or Semgrep Cloud (SaaS)
- **Languages:** Python, C#, JS, Go, Ruby, and many more
- **What it does:** Pattern-based static analysis with a highly flexible rule language. Community rules cover OWASP Top 10. Teams can write custom rules for project-specific patterns.
- **AI angle:** Semgrep Pro uses AI to generate fix suggestions; AI assistant for rule creation
- **Strengths:** Fast, lightweight, excellent for CI pipelines; custom rules enable organization-specific secure coding policy enforcement
- **Limitations:** Less IDE-integrated than SonarQube; rule tuning requires effort
- **Training suitability:** ⭐⭐⭐⭐ — good for showing customization and CI integration

---

### Snyk Code
- **Tool Type:** SAST (AI-powered)
- **SSDLC Phase:** Implementation, Testing, CI/CD gate
- **ISO27001 Controls:** A.8.28, A.8.29
- **Confidentiality Posture:** SaaS (code may be sent to Snyk servers); enterprise plan with tenant isolation
- **Languages:** Python, C#, JS, Java, and more
- **What it does:** AI-trained SAST engine that detects vulnerabilities in application code with low false positive rates. Provides fix suggestions and inline IDE feedback.
- **AI angle:** Core engine is AI-trained on millions of code patterns; fix suggestions are AI-generated
- **Strengths:** High accuracy; excellent developer UX; IDE plugins for VS Code and Rider
- **Limitations:** SaaS — code leaves the environment; cost for teams
- **Training suitability:** ⭐⭐⭐⭐ — good demo in IDE; important to discuss confidentiality trade-off

---

### GitHub Copilot Autofix (GitHub Advanced Security)
- **Tool Type:** SAST + AI-powered fix generation
- **SSDLC Phase:** Implementation, Code Review / PR
- **ISO27001 Controls:** A.8.28, A.8.29, A.8.32
- **Confidentiality Posture:** GitHub cloud; GitHub Enterprise Server for on-prem
- **Languages:** Python, C#, JavaScript, Java, Ruby, Swift
- **What it does:** GitHub's CodeQL engine detects vulnerabilities; Copilot Autofix generates code fixes directly in the PR, with an explanation for the developer.
- **AI angle:** AI generates the fix and the explanation; developer approves or modifies
- **Strengths:** Fully integrated into GitHub PR workflow; zero setup for teams already on GitHub; fixes are suggested, not auto-applied
- **Limitations:** Requires GitHub Advanced Security license; fix quality varies; cloud dependency
- **Training suitability:** ⭐⭐⭐⭐⭐ — excellent for showing the human-in-the-loop concept in action

---

### Checkmarx One (formerly CxSAST)
- **Tool Type:** Enterprise SAST + supply chain
- **SSDLC Phase:** Implementation, Testing, CI/CD gate
- **ISO27001 Controls:** A.8.28, A.8.29
- **Confidentiality Posture:** SaaS or on-premises
- **Languages:** Python, C#, Java, JS, and 30+ more
- **What it does:** Enterprise-grade SAST with AI-driven triage assistance, correlation engine, and developer-facing remediation guidance
- **AI angle:** AI-assisted result prioritization and fix guidance
- **Strengths:** Deep enterprise adoption; strong compliance reporting features; good audit trail
- **Limitations:** Complex setup; licensing cost
- **Training suitability:** ⭐⭐⭐ — good to mention, less suitable for hands-on demo

---

## Category 2 — AI-Assisted Dependency & Supply Chain (SCA)

### Snyk Open Source
- **Tool Type:** SCA (Software Composition Analysis)
- **SSDLC Phase:** Implementation, Testing, CI/CD gate
- **ISO27001 Controls:** A.8.29, A.8.32
- **Confidentiality Posture:** SaaS; enterprise plan available
- **What it does:** Scans project dependencies (pip, NuGet, npm, etc.) for known CVEs. Suggests upgrade paths and fix PRs. Monitors for newly disclosed vulnerabilities.
- **AI angle:** AI-generated fix PRs, prioritization based on reachability analysis
- **Strengths:** Seamless CI/CD integration; developer-friendly UX; actionable fix suggestions
- **Limitations:** SaaS — dependency manifests sent to Snyk; reachability analysis not always accurate
- **Training suitability:** ⭐⭐⭐⭐ — easy to demo with a requirements.txt or .csproj file

---

### OWASP Dependency-Check
- **Tool Type:** SCA (open source)
- **SSDLC Phase:** Testing, CI/CD gate
- **ISO27001 Controls:** A.8.29
- **Confidentiality Posture:** Fully local / self-hosted
- **What it does:** Scans dependencies against the NVD (National Vulnerability Database) for known CVEs. Generates HTML/XML/JSON reports.
- **AI angle:** No AI natively; can be combined with AI for report interpretation
- **Strengths:** Free, open source, no data leaves the environment — ideal for restricted client projects
- **Limitations:** Higher false positive rate; no fix suggestions; requires local NVD mirror for air-gapped use
- **Training suitability:** ⭐⭐⭐⭐ — excellent for demonstrating the "restricted environment" alternative

---

### GitHub Dependabot
- **Tool Type:** SCA + automated update PRs
- **SSDLC Phase:** CI/CD, Operations
- **ISO27001 Controls:** A.8.29, A.8.32
- **Confidentiality Posture:** GitHub cloud
- **What it does:** Automatically opens PRs to upgrade vulnerable dependencies. Monitors ecosystem advisories continuously.
- **AI angle:** No direct AI; works with Copilot Autofix in the same PR workflow
- **Strengths:** Zero configuration for GitHub repos; continuous monitoring; integrates with security policies
- **Limitations:** Cloud only; can generate noise if not configured for severity thresholds
- **Training suitability:** ⭐⭐⭐ — easy to show; best as a complement to Snyk/OWASP examples

---

## Category 3 — AI for Secret Detection

### GitGuardian
- **Tool Type:** Secret scanning + incident response
- **SSDLC Phase:** Implementation, CI/CD gate, Operations
- **ISO27001 Controls:** A.8.28, A.8.10 (Information deletion)
- **Confidentiality Posture:** SaaS; self-hosted option for enterprises
- **What it does:** Scans code commits, PRs, and history for leaked secrets (API keys, passwords, tokens, certificates). Sends real-time alerts. Covers 350+ secret types.
- **AI angle:** AI-powered secret classification and context analysis to reduce false positives
- **Strengths:** Very low false positive rate; covers all major VCS platforms; pre-receive git hooks to block commits
- **Limitations:** SaaS; historical scanning can surface old issues that need triage
- **Training suitability:** ⭐⭐⭐⭐⭐ — high-impact demo, universal pain point for developers

---

### TruffleHog (OSS)
- **Tool Type:** Secret scanning (open source)
- **SSDLC Phase:** Implementation, CI/CD gate
- **ISO27001 Controls:** A.8.28
- **Confidentiality Posture:** Fully local
- **What it does:** Scans git history and files for high-entropy strings and known secret patterns
- **AI angle:** No AI natively; entropy-based detection
- **Strengths:** Free, runs locally, good for restricted environments and git history audits
- **Training suitability:** ⭐⭐⭐ — useful to show open source alternative

---

## Category 4 — AI-Assisted Code Review

### GitHub Copilot (Coding Assistant)
- **Tool Type:** AI coding assistant
- **SSDLC Phase:** Implementation
- **ISO27001 Controls:** A.8.28 (via secure coding guidance)
- **Confidentiality Posture:** Cloud SaaS; GitHub Copilot Enterprise with org-level policy; no training on private code
- **What it does:** In-editor AI assistant that suggests code completions, generates functions from comments, explains code, and answers questions. Can be prompted for secure coding review.
- **AI angle:** Core product IS the AI
- **Strengths:** Massive productivity impact; can be used to generate secure code patterns, review code for issues, explain vulnerabilities; excellent for demonstrating spec-driven development
- **Limitations:** Can suggest insecure code; does not replace security review; cloud dependency
- **Key training message:** Copilot is a junior pair programmer — fast and helpful, but must be supervised. Every security-relevant suggestion must be validated.
- **Training suitability:** ⭐⭐⭐⭐⭐ — central tool for the training; ideal for live demos and exercises

---

### CodeRabbit
- **Tool Type:** AI-powered PR reviewer
- **SSDLC Phase:** Code Review / PR
- **ISO27001 Controls:** A.8.28, A.8.29, A.8.32
- **Confidentiality Posture:** SaaS; self-hosted option
- **What it does:** Automatically reviews every PR and provides inline comments on logic issues, security concerns, code quality, and missing test coverage. Summarizes the PR for reviewers.
- **AI angle:** Core product IS the AI; integrates into GitHub/GitLab PR workflow
- **Strengths:** Reduces human review burden; catches issues before human reviewer sees the PR; generates audit-friendly review summaries
- **Limitations:** SaaS; review quality varies; can miss domain-specific security patterns
- **Training suitability:** ⭐⭐⭐⭐ — good for showing automated review in the evidence chain

---

### Amazon CodeGuru Reviewer
- **Tool Type:** AI-powered code review (security + quality)
- **SSDLC Phase:** Code Review / PR
- **ISO27001 Controls:** A.8.28, A.8.29
- **Confidentiality Posture:** AWS cloud
- **Languages:** Python, Java
- **What it does:** ML-trained code reviewer that detects security vulnerabilities, credential exposure, and code defects. Integrates with GitHub and CodeCommit.
- **AI angle:** ML-trained on Amazon internal code and open source
- **Limitations:** Python and Java only (no .NET); AWS dependency
- **Training suitability:** ⭐⭐ — mention as ecosystem example; limited .NET relevance

---

## Category 5 — AI for Threat Modeling

### Microsoft Threat Modeling Tool (+ Copilot integration)
- **Tool Type:** Threat modeling
- **SSDLC Phase:** Design
- **ISO27001 Controls:** A.8.25, A.8.27
- **Confidentiality Posture:** Desktop tool (local); Copilot integration via cloud
- **What it does:** Creates data flow diagrams (DFDs) and automatically generates STRIDE-based threats. With AI assistance, can generate threat summaries and mitigation suggestions.
- **AI angle:** AI can assist in interpreting and explaining generated threats
- **Strengths:** Free; STRIDE native; familiar to .NET/Microsoft ecosystem; good audit artifact
- **Limitations:** Desktop-only; steep learning curve for diagrams; requires architectural knowledge
- **Training suitability:** ⭐⭐⭐ — worth explaining conceptually; full demo is time-consuming

---

### OWASP Threat Dragon
- **Tool Type:** Threat modeling (open source)
- **SSDLC Phase:** Design
- **ISO27001 Controls:** A.8.25, A.8.27
- **Confidentiality Posture:** Fully local / self-hosted
- **What it does:** Web-based or desktop threat modeling tool. Supports STRIDE, LINDDUN, CIA. Generates threat model documents.
- **AI angle:** No AI natively; can be combined with LLM prompts for threat generation
- **Strengths:** Free, open source, no data leaves environment
- **Training suitability:** ⭐⭐⭐ — good for showing lightweight threat modeling in constrained environments

---

### AI-Assisted Threat Modeling via LLMs (Methodology)
- **Tool Type:** Methodology (prompt engineering)
- **SSDLC Phase:** Design, Requirements
- **ISO27001 Controls:** A.8.25, A.8.26, A.8.27
- **Confidentiality Posture:** Depends on LLM used (cloud, enterprise, or local)
- **What it does:** Using a structured prompt with an architecture description, data flows, and sensitivity levels, an LLM (GPT-4, Claude, Copilot Chat) generates STRIDE threat lists, attack scenarios, and mitigation suggestions.
- **AI angle:** The LLM IS the tool; structured prompting is the skill
- **Strengths:** No dedicated tool needed; fast; adaptable; good for design-time quick threat review
- **Limitations:** Output quality depends entirely on prompt quality; must be validated; no diagram output; confidentiality risk if using cloud LLMs with sensitive architecture details
- **Example prompt pattern:** "You are a security architect. Given this data flow: [description], identify STRIDE threats for each component and suggest mitigations."
- **Training suitability:** ⭐⭐⭐⭐⭐ — excellent live demo; tangible output; teaches prompt discipline as a security skill

---

## Category 6 — Spec-Driven Development With AI

### Spec-Driven Development (Methodology)
- **Tool Type:** Methodology
- **SSDLC Phase:** Requirements, Design, Implementation
- **ISO27001 Controls:** A.8.25, A.8.26, A.8.28
- **Confidentiality Posture:** Independent of tool; applies to any LLM
- **What it does:** A development approach where detailed specifications (including security requirements, acceptance criteria, authorization rules, data handling constraints) are written before code is generated. The AI generates implementation from the spec, not from ambiguous prompts.
- **Why it matters for security:** Vague prompts produce vague (and often insecure) code. Specs that include security requirements produce code that attempts to satisfy them. The spec also serves as a traceable artifact for ISO27001 (A.8.26).
- **Key pattern:**
  1. Write specification: functional + security requirements + edge cases + error handling
  2. Review specification for completeness (human or AI-assisted)
  3. Generate implementation from spec
  4. Verify implementation against spec (automated tests + manual review)
  5. Store spec as evidence of requirements definition
- **Strengths:** Improves AI code quality dramatically; creates ISO27001-ready artifacts; forces security thinking before coding
- **Limitations:** Requires discipline and upfront investment; teams need to learn to write good specs
- **Training suitability:** ⭐⭐⭐⭐⭐ — core training concept; excellent for exercise design

---

## Category 7 — AI for Documentation & Compliance Evidence

### AI-Generated Security Documentation (Methodology)
- **Tool Type:** Methodology
- **SSDLC Phase:** All phases (cross-cutting)
- **ISO27001 Controls:** A.8.25–A.8.34, audit trail requirements
- **What it does:** Using AI to generate, summarize, or structure security-relevant documentation:
  - Security review summaries from code review sessions
  - Meeting notes capturing threat modeling discussions
  - Test coverage reports with security rationale
  - Change log entries with security impact notes
  - Risk assessment documentation
- **AI tools applicable:** GitHub Copilot Chat, Claude, GPT-4, local LLMs via Ollama
- **Key training message:** Evidence that is AI-assisted but human-reviewed and approved is still valid ISO27001 evidence. The human approval step is what matters.
- **Training suitability:** ⭐⭐⭐⭐ — easy to demonstrate; directly addresses the evidence imperative

---

## Category 8 — Local / Offline AI (for Confidential Environments)

### Ollama + Local Models (Llama 3, Mistral, CodeLlama, etc.)
- **Tool Type:** Local LLM runtime
- **SSDLC Phase:** Implementation, Design (any phase)
- **ISO27001 Controls:** A.8.10 (data confidentiality), A.8.12 (data leakage prevention)
- **Confidentiality Posture:** Fully local — nothing leaves the machine
- **What it does:** Runs open-source LLMs locally. Models like CodeLlama and Mistral can perform code review, explain vulnerabilities, assist with threat modeling, and support secure coding — entirely without internet access.
- **AI angle:** Full LLM capabilities, offline
- **Strengths:** Zero confidentiality risk; works in air-gapped or restricted client environments; free
- **Limitations:** Model quality lower than GPT-4 / Claude tier; requires capable hardware (8GB+ RAM minimum)
- **Training suitability:** ⭐⭐⭐⭐ — critical to mention as the "restricted environment" alternative; important for this consultancy audience

---

### LM Studio
- **Tool Type:** Local LLM desktop application
- **SSDLC Phase:** Implementation, Design
- **Confidentiality Posture:** Fully local
- **What it does:** Desktop UI for running local models. Provides a chat interface and a local OpenAI-compatible API endpoint. Models from Hugging Face can be loaded.
- **Strengths:** User-friendly; no command line needed; API endpoint allows integration with IDE plugins
- **Training suitability:** ⭐⭐⭐ — good to mention as accessible entry point for local AI

---

## Category 9 — AI Trust Model (Governance Framework)

### Human-in-the-Loop Secure AI Usage (Framework)
This is not a tool but the governing framework that should wrap every AI tool in the training.

| AI Activity | Allowed Without Review? | Human Verification Required |
|-------------|------------------------|----------------------------|
| Code suggestion (Copilot) | No | Developer reviews before commit |
| SAST findings (SonarQube, Semgrep) | No | Developer triages; false positives dismissed with rationale |
| AI-generated fix (Copilot Autofix) | No | Developer reviews, tests, approves |
| AI threat model output | No | Security-aware developer/architect validates |
| AI-generated documentation | No | Reviewer approves before storing as evidence |
| Dependency scan results | Partial (auto-block critical CVEs) | Medium/low findings reviewed by human |

**Confidentiality decision tree:**
1. Does the code/data belong to a client project? → Check client AI policy first
2. Is the tool cloud SaaS? → Do not upload sensitive code without explicit approval
3. No approval or restricted project? → Use local model (Ollama/LM Studio) or approved enterprise tool
4. Always: do not paste credentials, PII, or proprietary algorithms into any AI tool

---

## Summary Matrix

| Tool / Method | Phase | Type | Confidentiality | Demo Suitability |
|---------------|-------|------|-----------------|-----------------|
| SonarQube | Implementation / CI | SAST | Self-hosted or SaaS | ⭐⭐⭐⭐⭐ |
| Semgrep | Implementation / CI | SAST | Self-hosted or SaaS | ⭐⭐⭐⭐ |
| Snyk Code | Implementation / CI | SAST | SaaS | ⭐⭐⭐⭐ |
| GitHub Copilot Autofix | PR / Code Review | SAST + AI Fix | GitHub cloud | ⭐⭐⭐⭐⭐ |
| Checkmarx One | Implementation / CI | SAST | SaaS or on-prem | ⭐⭐⭐ |
| Snyk Open Source | CI / Dependency | SCA | SaaS | ⭐⭐⭐⭐ |
| OWASP Dependency-Check | CI / Dependency | SCA | Local | ⭐⭐⭐⭐ |
| GitHub Dependabot | CI / Operations | SCA | GitHub cloud | ⭐⭐⭐ |
| GitGuardian | CI / Operations | Secret scanning | SaaS | ⭐⭐⭐⭐⭐ |
| TruffleHog | CI | Secret scanning | Local | ⭐⭐⭐ |
| GitHub Copilot | Implementation | Coding assistant | GitHub cloud | ⭐⭐⭐⭐⭐ |
| CodeRabbit | PR / Code Review | AI PR reviewer | SaaS | ⭐⭐⭐⭐ |
| MS Threat Modeling Tool | Design | Threat modeling | Local | ⭐⭐⭐ |
| OWASP Threat Dragon | Design | Threat modeling | Local | ⭐⭐⭐ |
| LLM-assisted threat modeling | Design | Methodology | Depends on LLM | ⭐⭐⭐⭐⭐ |
| Spec-driven development | Requirements / Design / Impl | Methodology | Depends on LLM | ⭐⭐⭐⭐⭐ |
| AI documentation generation | Cross-cutting | Methodology | Depends on LLM | ⭐⭐⭐⭐ |
| Ollama + local models | Any | Local LLM runtime | Fully local | ⭐⭐⭐⭐ |
| LM Studio | Any | Local LLM desktop | Fully local | ⭐⭐⭐ |
| Human-in-the-loop framework | Cross-cutting | Governance | N/A | ⭐⭐⭐⭐⭐ |

---

*Document prepared for training design purposes — March 2026*
