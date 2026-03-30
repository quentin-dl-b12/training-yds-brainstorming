# SSDLC & ISO27001 — Presenter Primer
### Contextual foundation for the "AI in SDLC/SSDLC Workflows" workshop

> **How to use this document:** Read this before the session. You do not need to memorize it — you need to understand it well enough to explain concepts in plain language and acknowledge what you're simplifying. Keep the vocabulary table at the end open during the session for quick reference.
> **Estimated reading time:** ~10 minutes.

---

## Part 1 — SSDLC: Secure Software Development Lifecycle

### What it is

SSDLC stands for Secure Software Development Lifecycle. It is the practice of weaving security activities into every phase of software delivery — requirements, design, implementation, testing, deployment, and operations — rather than treating security as a final review gate before release. The core insight: a vulnerability found during design costs a few hours of conversation. The same vulnerability found after a production breach can cost far more.

Without SSDLC, security is "bolted on" — typically a brief pen test before go-live. With SSDLC, security is a *design property from day one*, not an afterthought.

### The phases, and what security adds

| Phase | What SSDLC Adds |
|---|---|
| Requirements | Define security requirements: authentication/authorization rules, data classification, compliance constraints |
| Design | Threat modeling: systematically identify what could go wrong and how an attacker could exploit the system |
| Implementation | Secure coding: input validation, secrets management, no hardcoded credentials, dependency hygiene |
| Testing | Security testing: SAST (static code analysis), SCA (dependency scanning), DAST (live app testing), pen testing |
| Deployment | Secure configuration: hardened environments, secret rotation, environment separation |
| Operations | Vulnerability monitoring, incident response, patching, security logging |

### Four concepts every developer should know

1. **Shift left** — move security activities earlier on the timeline. Earlier detection means lower cost, fewer production incidents, fewer audit findings.

2. **Threat modeling** — structured thinking about what could go wrong. The most accessible framework is **STRIDE**: Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege. A quick STRIDE pass on any new API endpoint or data flow is a practical, low-ceremony habit.

3. **SAST and SCA** — SAST (Static Application Security Testing) analyzes code without running it, catching vulnerability patterns like SQL injection, missing authorization checks, or hardcoded secrets. SCA (Software Composition Analysis) scans third-party dependencies for known CVEs. Both integrate into CI/CD pipelines as automated gates.

4. **Secure coding principles** — never trust input; fail securely; use least privilege; never roll your own crypto; keep secrets out of code and out of logs.

**The one sentence to internalize:** SSDLC is what happens when you stop treating security as someone else's concern and start treating it as a quality attribute — like performance.

---

## Part 2 — ISO27001: The Essentials

### What it is

ISO/IEC 27001 is the international standard for **Information Security Management Systems (ISMS)**. Organizations that hold ISO27001 certification have demonstrated — through an external audit — that they manage information security in a structured, documented, and auditable way.

**Critical nuance:** ISO27001 is a *management* standard, not a technical one. It does not prescribe which tools to use. It requires organizations to: identify information risks, implement controls to reduce those risks to acceptable levels, measure effectiveness, and continuously improve. It is the *why* and the *what* — SSDLC is the *how*.

### What the standard is made of

The standard has a main body (organizational requirements) and **Annex A** — a catalogue of 93 security controls organized into four themes:

| Theme | Scope |
|---|---|
| Organizational | Policies, roles, responsibilities, governance |
| People | HR security, awareness training |
| Physical | Physical security, equipment protection |
| **Technological** | **Access control, cryptography, logging, vulnerability management, secure development** |

### The developer-facing controls

Most of Annex A lives at the organizational level, but eight controls directly affect development teams:

| Control | What It Requires of Developers |
|---|---|
| A.8.25 | Security integrated throughout the full development lifecycle |
| A.8.26 | Security requirements defined at the requirements phase |
| A.8.27 | Architecture and design must account for security |
| A.8.28 | Secure coding practices must be followed and communicated |
| A.8.29 | Security testing during development |
| A.8.31 | Dev / test / prod environments must be separated; no production data in test |
| A.8.32 | Changes must follow a controlled process |
| A.8.34 | Audit logs must be protected and retained |

### The evidence imperative

ISO27001 certification is not a one-time badge — it requires ongoing audits. Auditors ask: *Can you show that security requirements were defined for this project? Can you show that a code review was conducted? Can you show scan results and that findings were addressed?*

**Nothing counts without documentation.** This is where AI tools become directly relevant: AI-assisted development can generate reviewable artifacts — spec documents, review summaries, scan reports — that directly serve ISO27001 evidence requirements.

### The risk-based approach

ISO27001 does not demand perfection. It demands *conscious decisions*. Not implementing rate limiting is accepting a risk — that should be a deliberate, documented choice, not an accidental omission. Every security decision in development is implicitly a risk decision.

---

## Part 3 — How SSDLC and ISO27001 Connect

> "ISO27001 is the *why* and the *what*. SSDLC is the *how*."

ISO27001 requires secure development (A.8.25). SSDLC provides the engineering practices that fulfill that requirement. ISO27001 requires evidence. SSDLC practices — code reviews, SAST reports, CI gate logs, spec documents — become that evidence. ISO27001 requires continuous improvement. SSDLC metrics feed that cycle.

For this workshop specifically: every time a developer uses AI to generate a spec, run a scan, or produce a review summary — they are simultaneously adopting SSDLC *and* generating ISO27001 evidence. That is the practical bridge.

---

## What to Say Confidently vs. What to Simplify

| Topic | Say confidently | When to simplify |
|---|---|---|
| SSDLC phases | "Security belongs at every phase, not just before release" | If asked about specific tooling per phase: *"There are many options — the session covers the most practical ones for your stack"* |
| ISO27001 purpose | "It's a management framework that requires documented evidence of security controls" | If asked about the audit or certification process: *"That's deep compliance territory — what matters for your daily work is the developer-facing controls in Annex A"* |
| STRIDE | "A quick way to think about threats: spoofing, tampering, repudiation, disclosure, denial of service, privilege escalation" | If asked about formal threat modeling methodologies: *"There are rigorous approaches — we'll see how AI makes a lightweight version practical in Block 5"* |
| Annex A controls | "Secure coding and security testing are explicitly required by ISO27001 — not optional" | If asked to enumerate all 93 controls: *"The full catalogue is public — what we focus on today are the 8 that land directly on teams like yours"* |
| SAST vs SCA vs DAST | "SAST analyzes code statically. SCA scans dependencies. DAST tests a running app. They catch different things." | If asked which is "better": *"In practice you want all three eventually. Start with SAST and SCA — they're the easiest to add to a pipeline."* |
| ISO27001 and AI | "AI tools can generate the artifacts that become your ISO27001 evidence — specs, review summaries, scan reports" | If asked whether ISO27001 explicitly allows or prohibits AI: *"ISO27001 doesn't say anything about specific tools. A.8.28 requires secure coding practices — AI-assisted coding is still subject to those practices."* |

---

## Key Vocabulary Reference

| Term | Short Definition |
|---|---|
| **ISMS** | Information Security Management System — the full set of policies, processes, and controls an organization uses to manage information security |
| **Annex A** | The catalogue of 93 security controls in ISO27001 |
| **Risk Assessment** | The process of identifying, analyzing, and evaluating security risks |
| **SoA** (Statement of Applicability) | The document where an organization lists which Annex A controls it applies and why |
| **Audit Trail / Evidence** | Documentation proving that a security control was applied |
| **Nonconformity** | An audit finding that a required practice is not being followed |
| **CVE** | Common Vulnerabilities and Exposures — a public identifier for known software vulnerabilities |
| **SAST** | Static Application Security Testing — automated code analysis for vulnerability patterns |
| **SCA** | Software Composition Analysis — dependency vulnerability scanning |
| **DAST** | Dynamic Application Security Testing — testing a running application for vulnerabilities |
| **Threat Modeling** | Structured analysis of potential attacks and design flaws |
| **STRIDE** | Threat modeling framework: Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege |
| **Shift Left** | Moving security activities earlier in the development process |
| **SSDLC** | Secure Software Development Lifecycle — integrating security across all delivery phases |
| **DevSecOps** | Culture and practice integrating security into DevOps workflows |

---

*Prepared for the "AI in SDLC/SSDLC Workflows" workshop — March 2026*
