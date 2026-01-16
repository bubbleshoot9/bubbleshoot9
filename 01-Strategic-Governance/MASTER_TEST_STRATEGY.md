# 🏛️ Master Test Strategy (MTS)

> **Standard:** TMMi Level 2 (Managed) & ISO 29119 Compliant  
> **Scope:** Enterprise-wide testing standards applicable to all squads.

---

## 1. 🎯 Objectives & Scope

This document defines the mandatory testing standards required to ensure that every release meets agreed business, quality, and risk expectations across the organisation.

* **Goal:** Achieve full visibility of product and delivery risk prior to deployment.
* **In-Scope:** All Web, Mobile, and API services delivered within the domain.
* **Out-of-Scope:** Third-party vendor internal implementations (validated via black-box testing only).

---

## 2. ⚖️ Risk-Based Testing (RBT) Approach

Testing effort is applied proportionally based on risk. We adopt an **Analytical (Risk-Based) Testing Strategy** to focus validation where failure would have the greatest impact.

1. **Risk Identification:** Conducted collaboratively during the [Three Amigos](../02-People-Operations/TEAM_WORKING_AGREEMENT.md).
2. **Risk Prioritisation:** Assessed using the [RBT Priority Matrix](./RBT_PRIORITY_MATRIX.md).
3. **Execution Depth:**
   * **Critical Risk:** Automated regression testing, manual exploratory testing, and full API contract validation.
   * **Low Risk:** Developer self-testing supported by automated smoke testing only.

---

## 3. 🏗️ Test Levels & Types

To support a **Shift-Left** quality approach, testing activities are distributed across the following standardised levels:

| Level | Responsibility | Type | Focus |
| :--- | :--- | :--- | :--- |
| **L1: Unit** | Developer | Automated | Business logic, boundary conditions, and method-level validation |
| **L2: Integration** | Dev / QA | Automated | API contracts, service interactions, and internal dependencies |
| **L3: System** | QA | Hybrid | End-to-end user journeys and cross-system workflows (UI) |
| **L4: Acceptance** | PO / UAT | Manual | Business value, usability, and legal or regulatory compliance |

---

## 4. 🚦 Entry & Exit Criteria (Quality Gates)

Features and changes may only progress through the delivery lifecycle when the following **Managed Quality Gates** are satisfied.

### Entry Criteria (Ready to Test)

* Requirements defined and approved in **Gherkin** format.
* Required test data available and appropriately sanitised.
* Code has successfully passed **L1 Unit Testing** with **greater than 80% coverage**.

### Exit Criteria (Ready to Ship)

* 100% of **High-Risk** test scenarios executed and passed.
* No open **Blocker** or **Critical** defects.
* A [Blameless RCA](../03-Operational-Delivery/BLAMELESS_RCA.md) completed for any production-like defects identified in Staging.

---

## 5. 🛠️ Test Environment & Data

* **Environments:**
  * Development (Isolated)
  * Staging (Production-like)
  * Production
* **Data Strategy:** Synthetic test data generated using **GenAI** for PII-sensitive scenarios. Live customer data must not be used in any non-production environment.

---

## 6. 📊 Defect Management

* **Tool:** Jira
* **Severity Levels:**
  * **S1 (Blocker):** Prevents further testing or release; immediate resolution required.
  * **S2 (Critical):** Core functionality unavailable with no viable workaround.
  * **S3 (Major):** Functional impact with an acceptable workaround.
  * **S4 (Minor):** Cosmetic defects or UI/UX inconsistencies.

---

## 7. 🔄 Regression Strategy

* **Automated Smoke Tests:** Executed on every Pull Request (**Gate 1**).
* **Automated Regression Suite:** Executed nightly (**Gate 3**).
* **Manual Regression:** Performed only where AI-driven risk analysis identifies a potential **Impact Gap**.

---

## 8. 🎓 Governance & Maintenance

* This Master Test Strategy is reviewed **annually**, or following any [Major Post-Mortem](./BLAMELESS_RCA.md).
* All squads must align their local **Sprint Test Plans** with this Master Strategy to ensure consistent quality governance.

---
