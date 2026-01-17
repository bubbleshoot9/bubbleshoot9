# 📊 Quality Engineering KPI Framework

> **Strategy:** Shift from *activity-based metrics* (“How much did we do?”) to *outcome-based metrics* (“How much risk did we remove and value did we create?”).

This framework measures quality **end-to-end**—from requirements through to post-release—ensuring metrics drive the *right behaviours*, not vanity reporting.

---

## 🏗️ 1. Shift-Left / Requirements Phase

*Goal: Measure defect prevention before a single line of code is written.*

| KPI | Target | Why It Matters to the Lead |
| :--- | :--- | :--- |
| **Requirement Ambiguity Rate** | < 10% | Indicates effectiveness of Three Amigos and early alignment |
| **Defect Injection Rate** | Downward trend | Confirms quality is being designed in, not tested in |

> Strong shift-left metrics reduce downstream cost exponentially.

---

## 🤖 2. Automation Engineering Phase

*Goal: Measure automation health, efficiency, and return on investment.*

| KPI | Target | Lead Action |
| :--- | :--- | :--- |
| **Automation Stability (Flakiness)** | > 98% pass | Quarantine unstable tests via the Pruning Policy |
| **Feedback Loop Time** | < 10 minutes | Scale CI/CD sharding to protect fast feedback |
| **In-Sprint Automation Coverage** | > 80% | Measures how closely automation tracks feature delivery |
| **Script Maintenance Ratio** | < 15% | Ensures automation remains an asset, not a liability |

> Automation velocity without stability is noise.

---

## 🚀 3. Execution & Release Phase

*Goal: Measure the effectiveness of quality gates and release confidence.*

| KPI | Target | Strategic Insight |
| :--- | :--- | :--- |
| **Defect Detection Percentage (DDP)** | > 90% | Confirms QA—not customers—find the majority of defects |
| **Test Execution Velocity** | Increasing | Reflects GenAI and parallelisation efficiency gains |
| **Mean Time to Detect (MTTD)** | < 1 hour | How quickly pipelines surface breaking changes |

> Fast detection is more valuable than perfect prevention.

---

## 🛡️ 4. Post-Release (Shift-Right)

*Goal: Measure real business impact and cost of quality.*

| KPI | Target | Executive Value |
| :--- | :--- | :--- |
| **Defect Leakage (P0 / P1)** | < 2% | Primary indicator of Risk-Based Testing effectiveness |
| **Mean Time to Repair (MTTR)** | < 4 hours | Demonstrates recovery capability and operational maturity |
| **Cost of Quality (CoQ)** | Decreasing YoY | Validates automation investment against bottom-line impact |

> Shift-right metrics close the loop between engineering and business outcomes.

---

## 🛠️ Implementation — “Metrics That Matter” Dashboard

All metrics are exposed via **live dashboards** (Allure, Grafana, PowerBI)—never manual spreadsheets.

Dashboards are designed to show:
- Risk coverage
- Release confidence
- Trend direction (not point-in-time snapshots)

> **Lead Narrative:**  
> “I don’t report on passed tests.  
> I report on **risk coverage** and **release confidence**.  
> If defect leakage is low and feedback is fast, engineering teams can move with autonomy and trust.”

---

This KPI framework ensures quality metrics enable **better decisions**, not defensive reporting—and positions Quality Engineering as a strategic business function.
