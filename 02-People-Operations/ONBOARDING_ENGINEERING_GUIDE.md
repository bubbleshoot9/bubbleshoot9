# 🤝 Team Onboarding: The High-Trust QA Way

> **Welcome to the Team!** This guide defines our *Triangle of Quality*: balancing **Human Intuition**, **Automated Guardrails**, and **AI Acceleration** to scale quality without slowing delivery.

---

## ⚖️ 1. The Triangle of Quality (Your Daily Balance)

We maintain a **5:1 Dev-to-QA ratio** by distributing effort intentionally across three complementary pillars:

| Pillar | Focus Area | Your Tooling |
| :--- | :--- | :--- |
| **🧠 Manual** | **Exploratory & UX:** Find what the requirements missed | Session-Based Charters, Persona Testing |
| **🤖 Automation** | **Regression & Speed:** Protect the “Golden Paths” | Playwright (TS), API Integration, CI/CD |
| **✨ AI-Augmented** | **Productivity & Analysis:** Eliminate low-value effort | GitHub Copilot, ChatGPT (Test Data / BPMN) |

> No single pillar wins alone—quality emerges from the balance.

---

## 🛠️ 2. Execution Standards: The Three Pillars

### 🧠 Manual Excellence (Exploratory Charters)

We do **not** write brittle, step-by-step manual scripts. We use **Exploratory Charters**:

- **Time-Boxed Sessions:** 60–90 minutes of focused, high-intent testing  
- **Persona-Driven:** Test as a *New User*, *Power User*, *Admin*, or *Adversarial Actor*  
- **Evidence Over Documentation:** Loom recordings or screenshots; prioritise *observability* over long reports  

---

### 🤖 Automation Standards (Playwright / TypeScript)

We follow the **10-Minute Rule**: the smoke suite must complete in under 10 minutes.

- **Atomic Tests:** One test, one purpose, one reason to fail  
- **Shift-Left by Default:** Skeleton automation is written *before* development completes  
- **API First:** If it can be validated via API (Gate 2), do **not** automate it via the UI  

---

### ✨ AI Integration (Augmented QA)

AI is an expected multiplier—not an optional experiment.

- **Test Data:** Use LLMs to generate complex JSON payloads and boundary conditions  
- **Boilerplate Reduction:** Use Copilot to generate Page Objects and repetitive Playwright selectors  
- **Log & RCA Analysis:** Use AI to scan large Splunk / Datadog logs to find root causes fast  

> AI accelerates thinking—it does not replace ownership or accountability.

---

## 🔄 3. The Sprint Workflow (10-Day Cycle)

| Days | Phase | Manual Focus | Automation Focus | AI Focus |
| :--- | :--- | :--- | :--- | :--- |
| **1–2** | Refinement | Logic “Sniff Test” | Testability Audit | BDD / Gherkin Drafting |
| **3–5** | Skeleton | Charter Planning | Page Object Creation | Mock Data Generation |
| **6–8** | Execution | **Exploratory Testing** | Script Execution | Log / Error Analysis |
| **9–10** | Hardening | Edge-Case Validation | Script Refactoring | RCA Summarisation |

---

## 🗣️ 4. Communication: The “Consultant” Voice

At *[Company Name]*, QA operates as a **delivery partner**, not a gatekeeper.

- **Instead of:** “This is broken.”  
- **Try:**  
  > “I explored the MFA flow under a simulated 3G network and observed a timeout after step two. Should we adjust the threshold for mobile users?”

- **AI Ethics:**  
  - Never paste client-sensitive data or PII into public AI tools  
  - Always sanitise data before using LLMs  

---

## 🏁 Your Success Metric

You are successful here if, by **Month One**, you can independently deliver a **Critical Feature** using the **Power of Three**:

1. A **CI-passing Automation Suite**  
2. A **Manual Charter Report** capturing real edge cases  
3. An **AI-Generated Data Set** covering 100+ meaningful scenarios  

> **Next Step:** Book a 15-minute 1-on-1 with the Lead QA Consultant to review your **Engineering Skills Matrix** and agree your first growth objectives.
