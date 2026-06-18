# blueprinted.io

**Structured knowledge governance for technical operations.**

Most operational knowledge lives in documents, wikis, and tribal memory. It drifts, contradicts itself, and rots the moment reality changes. Blueprinted is built on a different premise: knowledge should be governed the same way software is: versioned, reviewed, composable, and auditable.

The result is a platform where Tasks and Workflows are first-class governed records, not documents. Human reviewers approve changes before they land. AI agents and human workers consume the same data through the same API, with the same access rules.

---

## Repositories

| Repo | Description | Status |
|------|-------------|--------|
| [`core`](https://github.com/blueprinted-io/core) | Original MVP — FastAPI + SQLite, fully runnable locally | Complete |
| [`platform`](https://github.com/blueprinted-io/platform) | Production backend — PostgreSQL, async API, Authentik OIDC | Active development |
| [`app`](https://github.com/blueprinted-io/app) | React frontend | Active development |

**Start with `core`** if you want to understand the data model and governance lifecycle. It runs in under five minutes and has a seeded demo dataset.

**`platform` and `app`** are the production rebuild — the same model on proper foundations.

---

## The model

```
Domain
  └── Workflow          (a real-world outcome)
        └── Task        (an atomic unit of work)

Principle               (a standing rule that governs Tasks and Workflows)
```

Every record has a lifecycle: `draft → in_review → confirmed`. Changes go back to `in_review`. Nothing reaches production without a reviewer sign-off.

---

## Why

Learning and operational knowledge is still built like waterfall software — big launches, slow review cycles, content that's obsolete before it ships.

**LearningOps** is the alternative: treat knowledge like software. Build atomically, compose deliberately, review continuously, ship incrementally, keep everything auditable.

Full writeup: [docs/articles/learningops.md](https://github.com/blueprinted-io/core/blob/main/docs/articles/learningops.md)

---

## Live demo

[app.blueprinted.io](https://app.blueprinted.io/login) — running the MVP (`core`)

---

## License

`core` is licensed under the GNU Affero General Public License v3.0.  
`platform` and `app` are source-available, pre-release.
