# 🛠️ Developer Self-QA Checklist (Low / Medium Risk Features)

> **Purpose:** Enable fast, safe delivery of low-risk features by shifting quality ownership to the engineering source—without compromising standards.

When a feature is classified as **Tier 3 (Low Risk)** in the **RBT Priority Matrix**, Developers are expected to complete this checklist and attach evidence to the Jira ticket **before** moving it to **Done**.

This checklist replaces handoffs—not accountability.

---

## 🧪 1. Functional Verification

- [ ] **Positive Flow**  
  The feature behaves exactly as described in the User Story and Acceptance Criteria.

- [ ] **UI Consistency**  
  The implementation matches the approved design (spacing, fonts, colours, states).

- [ ] **Browser / Device Sanity Check**  
  Verified in at least one alternative browser or device context  
  *(e.g. Safari if developing on Chrome).*

---

## 🛡️ 2. Safety & Resilience

- [ ] **Error Handling**  
  Invalid input, empty states, or network interruption do not crash the application.

- [ ] **Console Hygiene**  
  No new console errors or warnings introduced by the change.

- [ ] **Accessibility (A11y) Basics**  
  Ran a browser accessibility tool (Axe, Wave, Lighthouse) and resolved obvious issues  
  *(contrast, labels, focus order).*

---

## ⚙️ 3. Automation, Observability & CI

- [ ] **Unit Test Coverage**  
  New or updated logic is covered by unit tests  
  **Minimum expectation:** 80% coverage for affected areas.

- [ ] **Observability**  
  Logs are meaningful, structured, and actionable  
  *(no generic “something went wrong” messages).*

- [ ] **Pipeline Health**  
  The build passes cleanly in CI/CD with no new warnings or failures.

---

## 🖇️ Evidence Requirements (“The Receipts”)

To move a ticket to **Done** without formal QA intervention, attach the following to the Jira ticket:

1. **UI Proof**  
   Screenshot or ≤10-second video showing the working feature flow.

2. **API / Network Proof**  
   Screenshot of a successful `200 OK` response for any new or modified API calls.

3. **Accessibility Proof**  
   Screenshot showing a green / pass result from the accessibility scan.

> Evidence is lightweight, but non-negotiable.

---

## 🧠 Leadership Note — *Why This Exists*

This is **not** “skipping QA.”  
It is **Distributed Quality Ownership**.

- Enables **Manual Testers** to focus on complex exploratory, usability, and security risks  
- Enables **Automation Engineers** to invest in scalable, stable, high-ROI frameworks  
- Empowers **Developers** to fully own the Definition of Done  

When quality starts at the source, speed and confidence increase together.

> **Fast delivery without discipline is luck.  
> Fast delivery with ownership is engineering.**
