# Presenter Reading List
### Everything the presenter needs to read before delivering the training

> **How to use this file:** Read each item in the order listed. Each entry indicates which sections matter most and why. The goal is to give you sufficient context to present confidently — not to make you an expert in every topic.

---

## Reading 1 — Audience & Training Design Context

**File:** [`brainstorming-session-2026-03-27-training-design.md`](brainstorming-session-2026-03-27-training-design.md)
**Start from section:** "Audience Profile (Synthesized)"
**Sections to read:**
- Audience Profile (Synthesized)
- Learning Objectives (Training-Ready)
- Non-Goals
- Central Training Promise
- Five Training Design Principles
- Three Additions to the Overall Design Process

**Why:** This tells you who is in the room, what they expect, what could go wrong, and what the training is trying to achieve. Read this first — it shapes how you frame everything else.

**Key things to remember:**
- Mixed junior/senior audience — layer your explanations
- Skepticism toward AI is expected: acknowledge it, don't fight it
- Consultancy context: examples must account for client constraints and tool access
- Primary learning objectives are 3, 4, and 6

---

## Reading 2 — SSDLC & ISO27001 Essentials

**File:** [`ssdlc-iso27001-essentials.md`](ssdlc-iso27001-essentials.md)
**Read in full.**

**Why:** This document gives you the conceptual foundation you need to speak confidently about SSDLC and ISO27001 during the training. You do not need to memorize it — you need to understand it well enough to explain concepts in plain language and answer basic questions.

**Key things to remember:**
- SSDLC = security integrated at every phase of software delivery, not bolted on at the end
- ISO27001 = a management standard. It says *what* must be managed. SSDLC is *how* developers do it.
- The developer-facing ISO27001 controls are in Annex A, section 8.25–8.34
- "Evidence" is the word that connects ISO27001 to daily dev work: code reviews, scan reports, CI logs
- Keep the Key Vocabulary Reference table handy during the training

---

## Reading 3 — Session Outline & Slide Content Guide

**File:** [`session-outline.md`](session-outline.md)
**Read in full.**

**Why:** This is your operational blueprint. It contains the full agenda with timings, what to say in each block, how to run the group discussions, how to facilitate the hands-on exercise, and what each slide group must contain. Read this last — after you have absorbed the audience profile and the SSDLC/ISO27001 context.

**Key things to remember:**
- This is a workshop, not a lecture. Your job is to guide, not to transfer knowledge.
- Every use case demo ends with a human judgment moment — always close the AI suggestion loop visibly.
- The hands-on (Block 8) is the most important 50 minutes. Prioritize it over everything if time runs short.
- The Monday shortlist (closing portion of Block 9) is the last substantive content participants hear. Keep it to 5 items maximum. Protect its simplicity.
- Expect skepticism from senior developers. It is a feature, not a problem — acknowledge it and use it.

---

## Reading 4 — Hands-On Exercise Facilitator Guide

**File:** [`hands-on-facilitator-guide.md`](hands-on-facilitator-guide.md)
**Read in full.**

**Why:** This is everything you need to run Block 8. It explains the exercise intent, walks through every file in the exercise repository, lists the intentional vulnerabilities and requirement gaps attendees are expected to discover, and gives phase-by-phase facilitation notes including what to say, what not to say, and how to cut if you are running behind.

**Key things to remember:**
- The goal is not a working implementation — it is awareness of what unstructured prompting misses
- Round 1 (vibe coding): stay silent, let people follow their instincts
- Debrief 1: ask the three questions, hold the tension — do not resolve it yet
- Round 2 (spec-driven): no prompt template is given on purpose; writing the prompt is part of the exercise
- Six security gaps are intentionally omitted from `requirements.md` — a good agent conversation surfaces most of them
- The exercise has worked if someone says "I could see doing this before every feature ticket"
