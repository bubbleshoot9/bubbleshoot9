# 🔍 Blameless Root Cause Analysis (RCA)

> **Core Principle:** Incidents are signals—not failures. Every issue is treated as an opportunity to strengthen our systems, processes, and safeguards. We fix *systems*, not people.

This framework defines a structured, blameless approach to RCA that prioritises learning, prevention, and continuous improvement.

---

## 🎯 When an RCA Is Required

An RCA is triggered for any of the following:

- **Production Incidents**  
  Any issue with direct customer or business impact.

- **Escaped Defects**  
  High or critical defects discovered in production that bypassed testing controls.

- **Process Breakdowns**  
  Failures caused by missing or bypassing agreed practices (e.g. skipping Three Amigos, incorrect RBT usage).

- **Near-Misses**  
  High-risk issues caught just before release—signals that the system *almost* failed.

> Near-misses are treated as first-class learning opportunities.

---

## ⚙️ The RCA Method — 5 Whys, System-Focused

We use a **5 Whys** technique to move beyond symptoms and identify underlying system gaps.  
The focus is always on *process, tooling, and decision-making*—never individuals.

---

### 🧪 Example RCA: Login Failure in Dark Mode

- **What Happened:**  
  Login failed for Safari users with Dark Mode enabled, blocking a critical user journey.

- **Impact:**  
  45-minute outage affecting ~2% of users, resulting in customer frustration and brand risk.

| Question | Finding | Category |
|--------|--------|---------|
| **Why did login fail?** | A CSS overlay blocked the “Sign In” button | Technical Defect |
| **Why wasn’t this detected earlier?** | Automation ran only in Light Mode | Automation Strategy Gap |
| **Why wasn’t Dark Mode tested manually?** | Exploratory charters didn’t include theming | Manual Coverage Gap |
| **Why wasn’t Dark Mode seen as high-risk?** | Treated as a UI enhancement, not a critical path | Risk Classification Error |
| **Why was risk misclassified?** | RBT framework didn’t include theme variance | Process Gap |

> The failure was not a person—it was a missing assumption.

---

## 🤖 Gen AI–Assisted RCA (Accelerator, Not Authority)

Gen AI is used to **accelerate insight**, not replace human judgment.

- **Pattern Analysis:**  
  AI can ingest logs, traces, and test results to surface correlations.

- **Incident Classification:**  
  Suggests whether the issue is likely technical, process, or coverage-related.

- **RCA Drafting:**  
  Produces an initial RCA narrative for human review and refinement.

> AI assists speed and clarity—but accountability remains human.

---

## 💡 RCA Outputs — Insights, Not Blame

The outcome of every RCA is a **set of system improvements**, never fault assignment.

From the example above:

- **Automation Gap:** Missing UI theme coverage  
- **Manual Gap:** Exploratory charters lacked visual risk guidance  
- **Process Gap:** RBT framework incomplete for presentation-layer risks  

---

## 🛠️ Corrective Actions (System-Level)

### 🚑 Immediate (Within 24 Hours)
- [ ] Add Dark Mode execution to Playwright configuration  
- [ ] Brief QA team on visual and theming regression risks  

---

### 🏗️ Structural (Next Sprint)
- [ ] Update RBT Priority Matrix to include *Visual & Theme Variants*  
- [ ] Extend Three Amigos checklist to cover accessibility and theming  

---

### 🌱 Long-Term (1–3 Months)
- [ ] Implement automated visual regression tooling  
- [ ] Run accessibility-first testing workshop (Dark Mode, WCAG, contrast)  

> Every RCA must result in at least one **permanent system improvement**.

---

## 💬 The Blameless RCA Meeting

- **Attendees:** QA Lead, Dev Lead, Product, and involved engineers  
- **Tone:** Curious, calm, and factual  
- **Key Question:** *“How did our system allow this?”*  
- **Anti-Pattern:** *“Who missed this?”*

Psychological safety is a prerequisite for honest learning.

---

## 🧠 Why Blameless RCA Works

### ✅ Blameless RCA = Stronger Systems
- Teams surface risks early  
- Root causes are actually fixed  
- Learning spreads across teams  
- Automation and manual testing evolve together  

### ❌ Blame-Based RCA = Repeat Failures
- Near-misses get hidden  
- Superficial fixes mask real issues  
- Fear replaces ownership  
- Teams fragment instead of improving  

---

## 📈 RCA Action Tracker (Sprint Governance)

*Tracks permanent improvements driven by RCA outcomes.*

| Incident ID | Root Cause | Permanent Action | Status |
| :--- | :--- | :--- | :--- |
| RCA-001 | Missing Auth Edge Case Coverage | Gate 1 updated to enforce 95% Auth coverage | ✅ Done |
| RCA-002 | Staging / Prod DB Drift | Automated schema validation added to Gate 2 | 🛠️ In Progress |

---

> **Blameless RCA is not about being soft—it’s about being effective.**
