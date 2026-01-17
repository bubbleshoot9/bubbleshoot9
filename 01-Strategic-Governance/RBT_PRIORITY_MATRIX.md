# ⚖️ Risk-Based Testing (RBT) Priority Matrix

> **Philosophy:** “Test what matters.” Apply manual testing where human judgement adds the most value, and automation where repeatability and scale deliver the strongest return.

This matrix forms the bridge between **business priorities** and **testing effort**. It provides a clear, data-driven framework to answer the key question:  
*Which areas should be tested manually, which should be automated, and where a hybrid approach is required?*

---

## 🎯 How to Use This Framework

1. **Assess Features:** During sprint planning, identify all new features, enhancements, or changes.
2. **Calculate Risk Score:** For each item, assess **Business Impact** and **Failure Risk** to derive an overall **Risk Score**.
3. **Define Testing Strategy:** Use the calculated score to determine the appropriate testing approach (Manual, Automated, or Hybrid) using the tables below.
4. **Allocate Resources:** Apply the **Execution Worksheet** to assign ownership, effort, and coverage expectations.

---

## The Decision Framework

| Feature Area | Business Impact | Failure Risk | Risk Score | Testing Strategy |
| :--- | :---: | :---: | :---: | :--- |
| **Primary Login (Happy Path)** | 5 | 1 | 5 | **Automated (Sanity)** – Baseline regression coverage |
| **MFA / 2FA Verification Flow** | 5 | 3 | 15 | **Manual + Automated** – Expert judgement with automation support |
| **Account Recovery (Lost Password)** | 4 | 4 | 16 | **Primary: Manual** – User empathy and edge-case validation |
| **UI Localization (Labels / Links)** | 1 | 1 | 1 | **Manual Spot-Check** – Occasional visual validation |
| **OAuth 3rd Party Integration** | 4 | 3 | 12 | **API Automation** – Contract and integration validation |

---

## 🧮 Risk Score to Strategy Mapping

Use this table to convert a **Risk Score** into a clear and consistent testing strategy.  
**Formula:** *Risk Score = Business Impact (1–5) × Failure Probability (1–5)*

| Score | Category | Strategy |
| :--- | :--- | :--- |
| **15–25** | 🔴 **Critical** | > **Exhaustive:** Full automation of core paths combined with senior manual exploratory testing for edge cases and failure modes. |
| **8–14** | 🟡 **Medium** | > **Hybrid:** Manual testing for new or complex business logic, supported by automation for regression and happy paths. |
| **1–7** | 🟢 **Low** | > **Minimal:** Primarily automated smoke coverage; manual testing only when specifically required. |

---

## 🛠️ Execution Worksheet (Sprint Template)

This worksheet is used during **Three Amigos** sessions or **Sprint Planning** to define the testing component of the *Definition of Done*.

| Feature Name | Risk Score | Logic Type | Manual Requirement | Automation Requirement |
| :--- | :---: | :--- | :--- | :--- |
| **Example: Apple Pay Integration** | **25** | New | 3 days exploratory testing (edge cases, network failures). | 100% path coverage (API + UI). |
| **Example: Update Footer Links** | **2** | Existing | None (spot-check only). | None (covered by global smoke). |
| **Example: Search Filter v2** | **12** | New | 1 day functional UI validation. | Automate happy path only. |

---

## 🔍 Deep Dive: Critical Logic Strategy (Score 15–25)

### 1. New Critical Logic (Discovery Focus)
> - **Mandatory:** One senior peer review of the test approach or plan.
> - **Technique:** **Negative and resilience testing** (invalid inputs, injection attempts, concurrency scenarios).
> - **Exit Criteria:** Zero open defects of any severity.

### 2. Existing Critical Logic (Protection Focus)
> - **Mandatory:** Completed **Impact Analysis** identifying all affected modules and integrations.
> - **Technique:** Full **Regression Suite** execution (must pass 100% at Gate 3).
> - **Exit Criteria:** No regressions detected in core “Golden Flows.”
