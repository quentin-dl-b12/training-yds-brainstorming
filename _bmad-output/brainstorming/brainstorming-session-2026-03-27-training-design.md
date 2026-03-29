---
stepsCompleted: [1, 2, 3]
inputDocuments: []
session_topic: 'Designing a 4-hour training on AI-enhanced SSDLC & ISO27001 for Python/.NET developers at a Tunisia-based consultancy'
session_goals: 'Define audience profile, learning objectives, and training design principles for a practitioner-grade AI+security training'
selected_approach: 'AI-recommended: Question Storming → Assumption Reversal → Role Playing'
techniques_used: ['Question Storming', 'Assumption Reversal', 'Role Playing']
ideas_generated: []
context_file: ''
---

# Brainstorming Session Results

**Facilitator:** Quentin
**Date:** 2026-03-27

---

## Session Overview

**Topic:** Designing a 4-hour training on AI-enhanced SSDLC & ISO27001
**Audience:** Junior and senior Python/.NET developers at a consultancy company in Tunisia. Company holds ISO27001 certification.
**Goals:** Produce a complete training design covering audience analysis, learning objectives, session plan, exercises, slides, and takeaways.

---

## Technique 1: Question Storming — Audience Discovery

The following questions were generated to map what must be validated before locking the training design:

### SSDLC & ISO27001 Maturity
- What is the actual spread of SSDLC maturity between juniors and seniors?
- How much of their ISO27001 familiarity is practical day-to-day behavior vs. awareness of company policy and audit vocabulary?
- Do they already connect ISO27001 requirements to concrete engineering practices (code review, secrets handling, dependency management, logging, traceability, change control)?
- How consistent are security practices across client projects, or does each team improvise based on customer constraints?
- Who usually owns security decisions during delivery: developers, tech leads, architects, DevSecOps, or compliance stakeholders?

### AI Tooling Reality
- How much freedom do developers have to introduce AI-assisted tooling on client engagements?
- Are they allowed to use cloud AI tools with source code, or are there confidentiality and client restrictions forcing local/approved enterprise tools only?
- Do they already use security tooling in CI/CD (SAST, dependency scanning, secret scanning, code quality gates, threat modeling, secure code review checklists)?

### Technical Context
- For .NET-heavy developers: which secure development topics are already familiar vs. basic/repetitive?
- For Python-heavy developers: where are the recurring risks (unsafe deserialization, dependency sprawl, packaging, secrets, weak input validation, API exposure)?
- What kinds of client environments do they work in most often (regulated sectors, public sector, enterprise internal apps, internet-facing products)?
- How often are they exposed to audit evidence requests tied to ISO27001 controls?

### Training Desiderata
- What would make this training feel immediately useful to a senior developer rather than "compliance theater"?
- What would make this training accessible for juniors without boring seniors?
- What examples would feel credible in Tunisia-based consultancy reality?
- Are they more likely to value AI for coding speed, security detection, documentation/compliance evidence, or design-time risk reduction?
- Where are they most likely to distrust AI (false positives, hallucinated fixes, confidentiality leakage, auditability, weak code suggestions)?
- What level of hands-on setup can the room tolerate in 4 hours without losing momentum?
- If they leave with only three practical habits to apply the next week, what would create the most value?
- What objections are likely: "We already do this," "ISO is for auditors," "AI is risky," "this slows delivery," "this doesn't work on real client code"?

---

## Technique 2: Assumption Reversal

Six dangerous default assumptions were identified and reversed:

| # | Default Assumption | Reversal |
|---|-------------------|----------|
| 1 | Since the company is ISO27001-certified, developers already understand SSDLC well | They may know the vocabulary but not the engineering implications |
| 2 | Experienced developers will naturally care about compliance | They may see compliance as bureaucracy unless tied to delivery pain and real code practices |
| **3** | **AI tools will be perceived as an upgrade** | **They may see AI as a source of confidentiality risk, bad fixes, and audit trouble** ⚠️ |
| **4** | **A single session can serve juniors and seniors equally** | **One group may be lost while the other is bored unless content is deliberately tiered** ⚠️ |
| 5 | Covering SSDLC and ISO27001 theory first is the best structure | Starting from concrete dev workflows and mapping back to the standards may work better |
| **6** | **Generic examples will transfer** | **Consultancy developers may dismiss examples that don't reflect client constraints and mixed-stack reality** ⚠️ |

**⚠️ Reversals identified as highest risk:** 3, 4, 6

---

## Technique 3: Role Playing — Three Voices in the Room

### Voice 1: Senior .NET Developer (skeptical of AI)
**Likely thinking:** "Don't sell me magic. Show me failure cases, limitations, and where AI helps in code review, threat spotting, dependency risk, or evidence generation."

**Needs from the session:**
- Concrete examples, not promises
- Failure cases and limitations of AI
- Clear human validation rules
- Workflow integration into PRs, CI, code review, secure coding

**What loses them:** generic "AI is the future" messaging, compliance-first framing, no discussion of false positives or hallucinations

### Voice 2: Junior Python Developer (curious but uneven on security)
**Likely thinking:** "I can code faster with AI but I'm not always sure when code is secure. I want practical guardrails."

**Needs from the session:**
- Simple mental models linking SSDLC to everyday engineering work
- Examples of secure and insecure AI-assisted coding behavior
- Clear "do this / don't do this" guidance
- Hands-on exercises with verification, not blind trust

**What loses them:** too much jargon, assumption everyone already understands security deeply, abstract governance talk

### Voice 3: Consultancy Delivery/Tech Lead (juggling clients and constraints)
**Likely thinking:** "Everything depends on client context, approved tools, confidentiality, and delivery pressure. If it doesn't work under constraints, it's not operational."

**Needs from the session:**
- Tooling patterns that work under restrictions
- Distinction between public SaaS AI, enterprise AI, and local/offline options
- Practical ways to produce evidence (review traces, generated documentation, security checks)
- A maturity model: what teams can adopt immediately, next, and later

**What loses them:** vendor-specific training with no fallback patterns, no treatment of confidentiality, no connection to repeatable evidence process

---

## Audience Profile (Synthesized)

- Mixed junior/senior developer audience at a Tunisia-based consultancy
- Some organizational familiarity with ISO27001 and SSDLC vocabulary; uneven practical understanding
- Likely skepticism toward AI unless framed as governed, constrained, and operationally realistic
- High need for examples in .NET and Python that are delivery-grade, not theoretical
- High value in showing AI as an assistant for secure coding, review, detection, documentation, and evidence generation

---

## Session Purpose (Updated)

**Primary goal:** Inspire participants to integrate AI tools into their SDLC/SSDLC workflows.
**Secondary goal:** Give them enough grounding to act on that inspiration immediately.

This is a **workshop**, not a training session. The framing is not "here is what you must learn" but "here is what is possible — and here is you trying it."

## Learning Objectives (Training-Ready)

By the end of the session, participants will be able to:

1. Recognize where AI tools fit in the SDLC and SSDLC lifecycle phases
2. Describe how ISO27001 influences engineering workflows without becoming compliance specialists
3. **⭐ Evaluate AI usage in development through two lenses: security value and compliance acceptability**
4. **⭐ Use AI responsibly for secure coding support, review assistance, vulnerability detection, and evidence generation**
5. Spot bad AI-assisted practices and explain why they are unsafe or non-compliant
6. **⭐ Adopt a practical workflow for AI-enhanced secure delivery that can survive client constraints and audits**

*(Objectives 3, 4, 6 are primary emphasis)*
*(Objective 1 now covers both SDLC and SSDLC)*

### Non-Goals
- Full ISO27001 practitioner training
- Deep .NET secure coding training from scratch
- Comprehensive threat modeling course
- Exhaustive overview of every AI security tool on the market
- Legal or certification interpretation training

---

## Central Workshop Promise

> "Participants will leave inspired to use AI as a controlled assistant inside their SDLC/SSDLC workflows — having seen it work, tried it themselves, and identified where it fits in their real projects."

---

## Five Training Design Principles

1. **Frame as pragmatic engineering, not AI evangelism**
2. **Teach AI with controls** — where it helps, where it fails, what humans must verify
3. **Layer for mixed seniority** — basic anchor + tradeoff/challenge case for each topic
4. **Use consultancy-grade examples** — client constraints, mixed tool access, delivery pressure, audit evidence
5. **Map every concept to developer behavior** — workflows first, then compliance mapping

---

## Three Additions to the Overall Design Process

1. Define a trust model for AI use (what is allowed, reviewed, never delegated, confidentiality protection)
2. Design content in two levels per section (foundation for juniors, advanced for seniors)
3. Build around realistic client constraints (ideal, restricted-environment alternative, evidence angle for each tool/method)
