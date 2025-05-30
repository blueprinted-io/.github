
# blueprinted.io

## What is blueprinted.io?

blueprinted.io is an **AI-native, task-driven learning engine** designed to kill the box-ticking LMS and finally make proof of capability the first-class citizen in organizational learning.

It’s **not** a course platform. It’s not for tracking “completion.” It’s not for engagement theater or dashboards nobody reads.  
It’s a system that transforms *real artifacts*—documentation, code, SOPs—into standardized, validated, auditable “learning objects” that demand evidence, not just clicks.

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
  │ (Docs, Code, │ ──▶ │ Ingestion   │ ──▶ │ (Learning Spec)  │ ──▶ │ Approval   │
  │   SOPs...)   │      └────────────┘      └──────────────────┘      └────────────┘
         │                                                             │
         ▼                                                             │
  ┌────────────────────────────────────────────────────────────────────┘
  │
  ▼
┌─────────────┐
│ Task Store  │  ◀─ SME-validated, versioned "learning objects"
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

## What’s a Learning Object?

Each “task object” is atomic, versioned, and has to be *proven*, not just completed.

| Field         | Description                                                 | Example                                                                                                                                                           |
|---------------|-------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `task`        | Short, output-driven description of the task                | Enable BitLocker on a Windows system drive and back up the recovery key.                                                                                          |
| `facts`       | List of factual knowledge or conditions needed              | - The drive must be formatted with NTFS<br>- TPM must be present or USB key used<br>- User must have admin rights                                                 |
| `concept`     | The reasoning, purpose, or “why” behind the task            | BitLocker encrypts data at rest; backing up the recovery key ensures recoverability in the event of lost credentials or hardware failure.                          |
| `procedure`   | Ordered list of actionable steps to complete the task        | 1. Open Control Panel > BitLocker Drive Encryption<br>2. Select “Turn on BitLocker” for the system drive<br>3. Choose unlock method (TPM/USB/password)<br>4. Save or print the recovery key<br>5. Complete the encryption process and verify status |
| `system_deps` | System-level requirements                                   | - Windows 10 Pro/Enterprise<br>- TPM chip or USB<br>- Sufficient disk space                                                 |
| `task_deps`   | List of prerequisite tasks                                  | - Verify hardware compatibility (`unconfirmed`)<br>- Ensure admin rights (`unconfirmed`)                                    |
| `confidence`  | Confidence assessment by the AI                             | Level: high<br>Score: 0.97<br>Reason: Procedure is standard, widely documented, and output is easily verifiable.             |
| `source`      | (Recommended) Source documentation, page, or URL            | https://learn.microsoft.com/en-us/windows/security/information-protection/bitlocker/bitlocker-overview                       |
| `id`          | (Recommended) Unique identifier for the task object         | windows-bitlocker-enable-backup                                                                                              |
| `status`      | (Recommended) Task status                                   | draft                                                                                                                        |
| `audit_log`   | (Recommended) Log of changes, reviewers, or SME sign-off    | - 2024-06-01: Created<br>- 2024-06-02: SME reviewed                                                                         |

Or if you prefer, we could look at something more 'real world' - although targeted at tech, the principles apply elsewhere too.

| Field         | Description                                                 | Example                                                                                                                                                       |
|---------------|-------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `task`        | Short, output-driven description of the task                | Reset a company-issued mobile device and ensure data is wiped before offboarding an employee.                                                                 |
| `facts`       | List of factual knowledge or conditions needed              | - Device must be returned by the employee<br>- Device PIN or password must be available<br>- Backup is required if any data must be retained                  |
| `concept`     | The reasoning, purpose, or “why” behind the task            | Wiping the device protects company and personal data, ensures GDPR/compliance, and prepares the hardware for re-issuance or secure disposal.                  |
| `procedure`   | Ordered list of actionable steps to complete the task        | 1. Retrieve device from employee<br>2. Verify device unlock credentials<br>3. Backup any required company data<br>4. Perform factory reset (Settings > System > Reset)<br>5. Confirm device is wiped<br>6. Update inventory records          |
| `system_deps` | System-level requirements                                   | - Access to device management portal (if used)<br>- Administrative rights for device<br>- Inventory system access                                             |
| `task_deps`   | List of prerequisite tasks                                  | - Collect device from departing employee (`unconfirmed`)<br>- Backup required data (`unconfirmed`)                                                            |
| `confidence`  | Confidence assessment by the AI                             | Level: high<br>Score: 0.92<br>Reason: Common business process, all actions well-documented and auditable                                                      |
| `source`      | (Recommended) Source documentation, page, or URL            | https://support.apple.com/en-gb/HT201274 (for iPhone)<br>https://support.google.com/android/answer/6088915 (for Android)                                      |
| `id`          | (Recommended) Unique identifier for the task object         | offboarding-device-reset                                                                                                                                      |
| `status`      | (Recommended) Task status                                   | draft                                                                                                                                                        |
| `audit_log`   | (Recommended) Log of changes, reviewers, or SME sign-off    | - 2024-06-01: Created<br>- 2024-06-02: HR reviewed                                                                                                            |

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

## License and Open Source Ethos

This project is **open source** under the [Apache 2.0 License](LICENSE.md) with a Commons Clause restricting direct SaaS resale.  
You are free to use, fork, and adapt blueprinted.io for commercial and non-commercial purposes—just don’t turn around and sell the core as a SaaS product without permission.

- Attribution is requested for any public or commercial use.
- See LICENSE.md for details.
- “blueprinted.io” and associated branding are trademarks of Ewan Matheson/blueprinted.io.

We strongly encourage contributions, peer review, and adaptation—if you make it better, please open a PR!

---

## Contributing

Contributions, feedback, and bug reports are welcome!  
If you’d like to contribute, please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

*If you’re a learning specialist, SME, or have ideas on proof models, your input is especially valuable.*

---

---

## Disclaimer

blueprinted.io is an independent open source project and is not affiliated with, endorsed by, or sponsored by any of the vendors or platforms referenced in its documentation or examples.

---

---

## What’s Next?

- CLI MVP for ingesting and querying learning objects
- SQLite-based task storage (upgradeable to Postgres)
- Web interface for human review and SME approval
- Automated AI ingestion pipeline for new docs

For more, see [ROADMAP.md](ROADMAP.md) (coming soon).

---


*This doc will evolve as the project moves from vision to working code. Want to challenge or contribute? Reach out at ewan@blueprinted.io.*
