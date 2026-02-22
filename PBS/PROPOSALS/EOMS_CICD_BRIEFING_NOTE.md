# EOMS — How Your Code Gets From Development to Production

**A Non-Technical Briefing Note for the Endeavour Team**

**Date:** 22 February 2026 | **Prepared by:** wings4mind.ai

---

## What This Document Covers

This note explains how changes to EOMS move safely from where they are built to where your team uses them every day. It covers the three environments, the promotion process, and why this matters for quality and control.

---

## The Three Environments

Think of EOMS as having three separate copies of the system, each with a specific purpose. Nothing goes live to your team without passing through all three stages.

### 1. Development (Dev)

**What it is:** The workshop. This is where the advisory team builds and tests new features, fixes issues, and experiments. It is a working environment — things may be incomplete or broken at times, and that is expected.

**Who uses it:** The advisory team (wings4mind.ai).

**What you might see:** Work in progress, partially built screens, test data.

### 2. Test

**What it is:** The quality check. When a feature is ready, it is promoted from Dev into Test. This is a clean, stable copy of the system where you and your team can review and try out new features before they go live.

**Who uses it:** Anthony, nominated traders (during UAT), advisory team.

**What you might see:** Completed features ready for your feedback. Real-looking data (but not live production data).

### 3. Production (Prod)

**What it is:** The live system. This is what your traders use every day to enter and manage orders. Only features that have been tested and approved in Test are promoted here.

**Who uses it:** All traders, operations, management.

**What you might see:** The real, working system with live data.

---

## How Changes Move Between Environments

```
   DEV                    TEST                   PROD
┌──────────┐          ┌──────────┐          ┌──────────┐
│          │          │          │          │          │
│ Build &  │ -------> │ Review & │ -------> │  Live    │
│ Fix      │ Promote  │ Approve  │ Promote  │  System  │
│          │          │          │          │          │
└──────────┘          └──────────┘          └──────────┘
  Advisory              Client +               Traders
  team works            Advisory               use daily
  here                  review here
```

**The key rule:** Changes only move forward. Dev to Test. Test to Prod. Never the other way around. This means your live system is always protected from unfinished or untested work.

### What "Promote" Means

Promotion is the act of moving a set of changes from one environment to the next. Each promotion is:

- **Deliberate** — someone specifically decides to move the changes forward
- **Reviewable** — before changes land in Test or Prod, there is a review step where someone checks what is being moved and approves it
- **Recorded** — every promotion is logged, so there is a complete history of what changed, when, and who approved it

### What Happens at Each Stage

| Stage | What Happens | Who Decides |
|-------|-------------|-------------|
| **Dev → Test** | Advisory team packages completed features and submits them for review | Advisory team proposes, Anthony reviews |
| **Test → Prod** | After UAT and client sign-off, approved features are promoted to live | Anthony recommends, James gives final go/no-go |

---

## Why This Matters

### Protection

Your live system is insulated from development activity. A bug introduced during development cannot affect your traders because it has to pass through Test first.

### Quality

Every feature gets reviewed in a stable environment before it reaches production. Traders test it, provide feedback, and issues are fixed before go-live.

### Control

You always know what is going live and when. No surprises. The promotion process gives you a clear approval point — nothing moves to production without your say-so.

### Traceability

Every change is tracked. If a question ever arises about when something changed or why, there is a complete record.

---

## What This Looks Like in Practice for EOMS Phase 1

Here is a concrete example of how a feature flows through the three environments:

**Example: Product Search Feature**

1. **Week 3 (Dev):** The advisory team builds the product search — connecting it to the 7,816 product codes, adding filters for market eligibility, brand, and feed type.

2. **Week 3 (Dev → Test promotion):** Once the feature works correctly in Dev, the advisory team promotes it to Test and notifies Anthony.

3. **Week 6 (Test — UAT):** During UAT, 3–5 traders try searching for products. They confirm search speed is acceptable, filters work as expected, and market eligibility displays correctly. Any issues found are fed back, fixed in Dev, and re-promoted to Test.

4. **Week 8 (Test → Prod promotion):** After UAT sign-off, the product search goes live as part of the production deployment. Traders can now use it with real data.

---

## Your Role in This Process

| Role | What You Do |
|------|-------------|
| **Anthony (CFO/COO)** | Review features in Test, approve promotions to Prod, coordinate UAT |
| **Traders (UAT)** | Test features in the Test environment, provide feedback on usability and correctness |
| **James (CEO)** | Final go/no-go authority for production deployment |
| **Advisory (wings4mind.ai)** | Build in Dev, promote to Test, fix issues, promote to Prod after approval |

You do not need to understand the technical mechanics. Your job is to **use the Test environment, tell us what works and what does not, and give the green light when you are satisfied**.

---

## Frequently Asked Questions

**Can a change go straight from Dev to Prod?**
No. Every change must pass through Test first. This is a deliberate safeguard.

**What if something goes wrong in Production?**
We can roll back to the previous version quickly. The three-environment setup means we always have a known-good version to revert to.

**Can traders access the Dev or Test environments?**
Traders access Test during UAT sessions. Dev is advisory-only. In normal operation, traders only use Prod.

**How often will changes be promoted?**
During the 8-week build, promotions to Test will happen as features are completed (roughly weekly). Promotion to Prod happens once at go-live, and then as needed for future updates.

**Who decides what goes into each promotion?**
The advisory team proposes what is ready. Anthony reviews and approves. For the final production deployment, James gives the go/no-go.

---

## Glossary

| Term | Plain English |
|------|---------------|
| **CI/CD** | Continuous Integration / Continuous Delivery — the overall practice of automatically building, testing, and delivering software changes in a structured, repeatable way. Think of it as the assembly line for software. |
| **Environment** | A separate, self-contained copy of the system. EOMS has three: Dev, Test, and Prod. Each serves a different purpose. |
| **Dev (Development)** | The workshop environment where new features are built and initially tested by the advisory team. |
| **Test** | The quality assurance environment where completed features are reviewed and approved before going live. |
| **Prod (Production)** | The live environment that traders use every day with real data. |
| **Promotion** | The controlled process of moving changes from one environment to the next (Dev → Test → Prod). |
| **Pull Request (PR)** | A formal request to move changes into an environment. It includes a description of what changed and requires approval before the changes are accepted. Think of it as a change request form. |
| **Branch** | A separate working copy of the code where changes are made without affecting the main system. Once the work is complete, the branch is merged back in via a pull request. |
| **Branch Protection** | A safety rule that prevents changes from being pushed directly into Test or Prod without going through a pull request and approval. It enforces the review step. |
| **Merge** | The act of accepting a pull request and incorporating the changes into the target environment. |
| **Rollback** | Reverting the system to a previous known-good version if something goes wrong after a deployment. |
| **Deployment** | The process of making a new version of the software available in an environment — particularly in Prod where traders use it. |
| **UAT (User Acceptance Testing)** | The phase where real users (traders) test new features in the Test environment and confirm they work as expected before go-live. |
| **Repository (Repo)** | The central store where all the code and documents for EOMS are kept. EOMS has three repos — one for each environment (dev, test, prod). |
| **Git** | The version control system that tracks every change made to the code. It keeps a complete history so nothing is ever lost. |
| **GitHub** | The online platform where the EOMS repositories are hosted. It provides the pull request workflow, branch protection, and change history. |
| **Pipeline** | The automated sequence of steps that code goes through when being promoted — checking for errors, running tests, and deploying to the target environment. |
| **Go/No-Go** | The formal decision point where stakeholders decide whether the system is ready for production. |

---

*Prepared by wings4mind.ai for the Endeavour team | 22 February 2026*
