# SSDLC & ISO27001 Essentials
### A Practical Primer for Training Presenters

> **Who this document is for:** Someone who will present a training on AI-enhanced SSDLC and ISO27001 compliance, but has limited prior exposure to these topics. This document gives you enough context to explain concepts confidently and correctly, without turning you into a compliance specialist.

---

## Part 1 — SSDLC: Secure Software Development Lifecycle

### What is SSDLC?

SSDLC stands for **Secure Software Development Lifecycle**. It is a methodology that integrates security practices into every phase of software development — from requirements gathering to deployment and maintenance.

The core insight is simple: **security problems are much cheaper to fix early than late**. A vulnerability found during design costs a few hours of discussion. The same vulnerability found after a production breach can cost millions and reputation damage.

Without SSDLC, security is typically "bolted on" at the end — often as a brief penetration test before go-live. With SSDLC, security is woven into the entire delivery process.

---

### SSDLC Is Not a New Idea

SSDLC has existed for decades. Two well-known frameworks define it in practice:

- **Microsoft SDL (Security Development Lifecycle)** — introduced by Microsoft in the early 2000s after a catastrophic wave of Windows vulnerabilities. Became a blueprint for enterprise secure development.
- **OWASP SAMM (Software Assurance Maturity Model)** — an open framework for measuring and improving software security across the full delivery lifecycle.

Both frameworks organize security activities by **SDLC phase**: requirements, design, implementation, testing, deployment, and operations.

---

### The SSDLC Phases and What Security Looks Like in Each

| Phase | What Normally Happens | What SSDLC Adds |
|-------|----------------------|-----------------|
| **Requirements** | Functional requirements gathered | Security requirements defined: authentication, authorization, data protection, audit logging, compliance constraints |
| **Design** | Architecture and data flows designed | Threat modeling: identify what could go wrong and how attackers could exploit the system |
| **Implementation (Coding)** | Developers write code | Secure coding practices: input validation, output encoding, secrets management, no hardcoded credentials, dependency hygiene |
| **Testing** | Functional and unit tests | Security testing: SAST (static analysis), SCA (software composition analysis), DAST (dynamic analysis), penetration testing |
| **Deployment** | Code released to production | Secure configuration: hardened environments, infrastructure as code reviews, secret rotation, access controls |
| **Operations & Maintenance** | System monitored, bugs fixed | Incident response plans, vulnerability management, patching, security logging and monitoring |

---

### Core SSDLC Concepts Every Developer Should Know

#### 1. Threat Modeling
The practice of systematically asking: "What could go wrong? Who might attack us? What are the most dangerous attack paths?"

The most common framework is **STRIDE**, originally from Microsoft:
- **S**poofing — Can an attacker pretend to be someone else?
- **T**ampering — Can they modify data?
- **R**epudiation — Can they deny having done something?
- **I**nformation Disclosure — Can they read things they shouldn't?
- **D**enial of Service — Can they make the system unavailable?
- **E**levation of Privilege — Can they gain more access than they should have?

Threat modeling does not require a specialist. Developers can do a quick version during design or code review by asking STRIDE questions about each component or API endpoint.

#### 2. Secure Coding Principles
Foundational rules that apply regardless of language or framework:

- **Never trust input**: validate and sanitize all input from users, external APIs, files, or databases.
- **Fail securely**: errors should not expose stack traces, sensitive data, or internal paths.
- **Least privilege**: code should only request the permissions it absolutely needs.
- **Defense in depth**: do not rely on a single security control. Layer them.
- **Never roll your own crypto**: use established libraries. Implement nothing from scratch.
- **Secrets belong in vaults, not in code**: API keys, passwords, connection strings must never be hardcoded.

#### 3. SAST and SCA
Two categories of automated security testing that integrate into CI/CD pipelines:

- **SAST (Static Application Security Testing):** analyzes source code without running it. Detects common vulnerability patterns such as SQL injection, XSS, insecure deserialization, and hardcoded secrets. Tools: SonarQube, Semgrep, Checkmarx, Snyk Code.
- **SCA (Software Composition Analysis):** scans third-party dependencies for known vulnerabilities. If you use a library that has a CVE, SCA catches it. Tools: OWASP Dependency-Check, Snyk Open Source, GitHub Dependabot.

#### 4. Shift Left
A key SSDLC term. "Shift left" means moving security activities earlier in the development process (to the "left" on a timeline). Instead of testing for security before release, you test for it during coding and design. Cheaper, faster, and more effective.

#### 5. Security Gates in CI/CD
Automated checkpoints in the CI/CD pipeline that block or warn on security issues:
- Build fails if SAST finds high-severity vulnerabilities
- PRs require security review or pass automated scans
- Deployment blocked if secrets are detected in code

---

### SSDLC in a Consultancy Context

Consultancy developers face a particular challenge: **security practices vary by project and client**. Some clients demand rigorous secure development. Others have no requirements at all. SSDLC provides a portable set of habits that developers can apply consistently regardless of client maturity.

For developers in a team that already holds ISO27001 certification, SSDLC is the **engineering expression** of security management. ISO27001 says "you must manage secure development." SSDLC is how you actually do it.

---

## Part 2 — ISO27001: The Essentials

### What is ISO27001?

ISO/IEC 27001 is the international standard for **Information Security Management Systems (ISMS)**. Organizations that achieve ISO27001 certification have demonstrated that they manage information security in a structured, documented, and auditable way.

**Key point:** ISO27001 is a management standard, not a technical standard. It does not specify exactly which technologies to use. It specifies that an organization must:
1. Identify what information assets they have and what risks threaten them
2. Implement controls to reduce those risks to acceptable levels
3. Monitor, measure, and continuously improve their security posture
4. Prove this through documented evidence

---

### What "Certification" Actually Means

When a company holds ISO27001 certification, it means:
- An external audit body assessed their ISMS against the standard
- They demonstrated sufficient documented controls and processes
- They will be re-audited periodically to maintain the certificate

It does **not** mean the company is unhackable, or that every employee has deep security knowledge. It means the organization has a governance framework in place.

---

### The Structure of ISO27001

ISO27001 is built around two documents:
- **The standard itself (ISO/IEC 27001:2022):** defines requirements for the ISMS — what a company *must* do
- **Annex A:** a catalogue of 93 security controls organized into 4 themes. Companies select which controls apply to them based on a risk assessment.

The four control themes in the 2022 version:
| Theme | Scope |
|-------|-------|
| **Organizational** | Policies, roles, responsibilities, governance |
| **People** | HR security, awareness, training |
| **Physical** | Physical security, equipment protection |
| **Technological** | Access control, cryptography, logging, malware protection, vulnerability management, secure development |

---

### The Developer-Facing Controls

Most of ISO27001 lives in the organizational/governance layer, but Annex A contains controls that directly affect developers. The most relevant:

| Control | What It Requires of Developers |
|---------|-------------------------------|
| **A.8.25 — Secure development lifecycle** | Security must be integrated throughout the development process |
| **A.8.26 — Application security requirements** | Security requirements must be identified at the requirements phase |
| **A.8.27 — Secure system architecture** | Architecture and design must consider security |
| **A.8.28 — Secure coding** | Secure coding practices must be followed and communicated |
| **A.8.29 — Security testing** | Security testing must be performed during development |
| **A.8.30 — Outsourced development** | Third-party development must include security requirements |
| **A.8.31 — Development/test/production separation** | Environments must be separated; production data must not be used in test |
| **A.8.32 — Change management** | Changes must follow a controlled process |
| **A.8.33 — Test information** | Test data must be carefully selected and protected |
| **A.8.34 — Audit and protection of information systems** | Audit logs must be protected and retained |

---

### The Risk-Based Approach

ISO27001 does not say "you must use tool X" or "you must have policy Y." Instead, it requires organizations to:

1. **Identify risks** — what could go wrong, how likely, how severe
2. **Decide how to treat each risk** — mitigate, accept, transfer, or avoid
3. **Implement controls** to support the chosen treatment
4. **Monitor effectiveness** — are the controls working?
5. **Improve continuously** — if controls fail or risks change, update them

This risk-based approach is important for developers to understand: every security decision during development is implicitly a risk decision. Not implementing input validation is accepting a risk. It should be a conscious choice with documentation, not an accidental omission.

---

### How ISO27001 and SSDLC Relate

A simple way to explain it:

> "ISO27001 is the *why* and the *what*. SSDLC is the *how*."

- ISO27001 requires secure development. SSDLC provides the engineering practices that fulfill that requirement.
- ISO27001 requires evidence. SSDLC practices like code reviews, SAST reports, scan results, and CI gate logs become that evidence.
- ISO27001 requires continuous improvement. SSDLC metrics (vulnerability trends, security debt, mean time to remediate) feed that improvement cycle.

---

### The Evidence Imperative

One of the most practically important aspects of ISO27001 for developers: **nothing exists without evidence**.

Auditors will ask:
- Can you show that security requirements were defined for this project?
- Can you show that a code review was conducted?
- Can you show scan results and that findings were addressed?
- Can you show that environments are separated?
- Can you show that developers received security training?

This is where AI tools become directly relevant. AI-assisted development can generate artifacts: review summaries, scan reports, documentation, and audit trails. If these are captured and stored, they directly serve ISO27001 evidence requirements.

---

### Key Vocabulary Reference

| Term | Short Definition |
|------|-----------------|
| **ISMS** | Information Security Management System — the full set of policies, processes, and controls an organization uses to manage information security |
| **Annex A** | The catalogue of 93 security controls in ISO27001 |
| **Risk Assessment** | The process of identifying, analyzing, and evaluating security risks |
| **Statement of Applicability (SoA)** | The document where an organization lists which Annex A controls it applies and why |
| **Audit Trail / Evidence** | Documentation proving that a security control was applied |
| **Nonconformity** | A finding during an audit that a required practice is not being followed |
| **CVE** | Common Vulnerabilities and Exposures — a public identifier for known software vulnerabilities |
| **SAST** | Static Application Security Testing — automated code analysis for vulnerabilities |
| **SCA** | Software Composition Analysis — dependency vulnerability scanning |
| **DAST** | Dynamic Application Security Testing — testing a running application for vulnerabilities |
| **Threat Modeling** | Structured analysis of potential attacks and design flaws |
| **Shift Left** | Moving security activities earlier in the development process |
| **Secure SDLC / SSDLC** | Integrating security practices across all software delivery phases |
| **DevSecOps** | A culture and practice that integrates security into DevOps workflows |

---

## Part 3 — The Connection to This Training

The training you will present is not about turning developers into ISO27001 auditors or security specialists. It is about one specific and practical goal:

> **Using AI as a controlled assistant to make SSDLC practices faster, more consistent, and more auditable — without replacing developer judgment.**

Here is how the major topics of the training connect to what you have just read:

| Training Topic | SSDLC Connection | ISO27001 Connection |
|----------------|-----------------|---------------------|
| AI for secure code review | Secure coding (SSDLC implementation phase) | A.8.28 Secure coding, A.8.29 Security testing |
| AI-assisted SAST (e.g. SonarQube) | Security testing, CI/CD gates | A.8.29 Security testing, A.8.32 Change management |
| AI for threat modeling assistance | Threat modeling (design phase) | A.8.25 SSDLC, A.8.27 Architecture |
| Spec-driven development with AI | Requirements and design phase security | A.8.26 Security requirements |
| AI for documentation and evidence generation | Audit trail, evidence | A.8.34 Audit logs, continuous improvement |
| AI trust model and governance | Human oversight, responsible use | ISMS risk treatment, A.8.25 |
| Confidentiality constraints on AI tool usage | Code confidentiality | A.8.10 Information deletion, A.8.12 Data leakage prevention |

---

*Document prepared for training design purposes — March 2026*
