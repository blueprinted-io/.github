
# blueprinted.io

## What is blueprinted.io?

blueprinted.io is an **AI-native, task-driven learning engine** designed to kill the box-ticking LMS and finally make proof of capability the first-class citizen in organizational learning.

It’s **not** a course platform. It’s not for tracking “completion.” It’s not for engagement theater or dashboards nobody reads.  
It’s a system that transforms *real artifacts*—documentation, code, SOPs—into standardized, validated, auditable “task objects” that demand evidence, not just clicks.

---

## Why Build This?

Because most learning systems are built for *compliance*—not for building or measuring *real skill*.  
SMEs waste their time authoring endless, generic content; learners click through and forget it all; “proof” is a joke.

**blueprinted.io exists for the 10% of teams who actually want to know if someone can do the work, not just say they finished the course.**

---

## How Does It Work?

**The core loop is brutally simple:**

```ascii
  ┌──────────────┐      ┌────────────┐      ┌──────────────────┐      ┌────────────┐
  │   Artifacts  │      │   AI Task  │      │  Human Review    │      │ SME /      │
  │ (Docs, Code, │ ──▶  │ Ingestion  │ ──▶  │ (Learning Spec)  │ ──▶  │ Approval   │
  │   SOPs...)   │      └────────────┘      └──────────────────┘      └────────────┘
         │                                                             │
         ▼                                                             │
  ┌────────────────────────────────────────────────────────────────────┘
  │
  ▼
┌─────────────┐
│ Task Store  │  ◀─ SME-validated, versioned "task objects"
└─────────────┘
      │
      ▼
┌────────────────────┐
│ Conversational AI  │  ◀─ Learner interface
│ (no dashboards)    │
└────────────────────┘
      │
      ▼
┌───────────────┐
│ Evidence      │ ◀─ Learner submits proof for each task (code, config, reasoning, etc.)
│ Submission    │
└───────────────┘
      │
      ▼
┌───────────────────────────────┐
│ Audit Trail / Validation Log  │ ◀─ SME signs off, system logs everything for proof
└───────────────────────────────┘
```

---

## What’s a Task Object?

Each “task object” is atomic, versioned, and has to be *proven*, not just completed.

```ascii
┌───────────────────────────────────────────────┐
│                Task Object                    │
├───────────────────────────────────────────────┤
│ ID: unique-task-id                            │
│ What: ("Configure X in Product Y v2.1")       │
│ Why: ("Ensures secure storage...")            │
│ How: ("Steps: 1... 2... 3...")                │
│ Source: (Doc/page/ref)                        │
│ SME Validator: (name, date, version)          │
│ Evidence Required: (code, file, explanation)  │
│ Status: (draft/approved/retired)              │
│ Audit Trail: (every change logged)            │
└───────────────────────────────────────────────┘
```

---

## Core Principles

- **AI-Native by Design:**  
  AI parses artifacts, proposes tasks, and delivers learning—but only humans (learning specialists, SMEs) approve, enrich, and validate.
- **Proof Over Completion:**  
  No “completed” buttons—learners must *prove* each task. SME signs off, system logs it.
- **Minimal UI:**  
  No dashboards. The learner just asks, “What do I need to learn?” and the AI surfaces the relevant task(s).
- **Audit Everything:**  
  Every change, review, approval, and submission is logged—orgs can finally show *real* capability, not just course history.
- **No Gamification, No Engagement Theater:**  
  The only metric that matters is “can you do the task?”

---

## Out of Scope (For Now)

- Best practices workflow (future add-on)
- SCORM/xAPI delivery (legacy for ingest/audit only)
- Dashboards, badges, leaderboards
- Public API or plugin system (post-MVP consideration)
- Open repo—private until the core loop is proven

---

## Who’s It For?

- Teams that *must* prove skill, not just seat time
- High-performance tech, SaaS, compliance-heavy, or risk-driven orgs
- SMEs who are sick of being content bottlenecks

---

## Where This Might Break

- “Proof” of skill is a hard, unsolved problem—feedback wanted on evidence models, SME workflow, and edge cases.
- Scale—does the approval loop hold up in large orgs?
- What’s missing for *your* use case? (Pull requests welcome after MVP.)

---

## Philosophy & Invitation

> “If you want dashboards and certificates, look elsewhere.  
If you want proof, capability, and growth—welcome to blueprinted.io.”

---

*This doc will evolve as the project moves from vision to working code. Want to challenge or contribute? Reach out at ewan@blueprinted.io.*
