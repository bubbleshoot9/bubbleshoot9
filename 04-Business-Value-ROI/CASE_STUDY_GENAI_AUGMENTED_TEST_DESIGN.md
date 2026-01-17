# 🤖 Case Study: GenAI-Augmented Test Design

> **Objective:** Reduce the *Requirement-to-Test* lifecycle by **~80%** through controlled use of Large Language Models (LLMs).

---

## 📋 The Problem

In high-velocity, security-sensitive areas (e.g. authentication flows), **test design—not execution—was the primary bottleneck**.

For each new feature:

1. QA spent **2–4 hours** analysing PRDs and user stories  
2. Manually authored Gherkin scenarios  
3. Mapped scenarios to existing Page Objects and automation structures  

This created friction at the exact point where speed and accuracy mattered most.

---

## 💡 The Solution — Shift-Left AI Test Design Utility

I designed a **GenAI-assisted workflow** that acts as a *co-pilot* for QA—accelerating test design while preserving human ownership and accountability.

LLMs are used to **generate drafts**, not make decisions.

---

## 🔄 The Workflow

1. **Extraction**  
   - Pulls the raw User Story and Acceptance Criteria directly from Jira  

2. **Synthesis**  
   - A controlled *System Prompt* instructs the LLM to generate:
     - Positive and negative test scenarios  
     - Boundary value analysis (e.g. password length, retry limits)  
     - Security and compliance considerations (MFA, GDPR, lockouts)  

3. **Drafting**  
   - Outputs:
     - Structured Gherkin (`.feature`) files  
     - Initial Playwright locator suggestions aligned to existing POMs  

4. **Human-in-the-Loop Validation**  
   - QA Lead reviews, edits, and approves all output  
   - Ensures **knowledge sovereignty**, correctness, and risk alignment  

> AI accelerates *thinking*, it does not replace *judgement*.

---

## 📈 Measurable Impact

| Metric | Before AI | After AI | Improvement |
| :--- | :--- | :--- | :--- |
| **Test Case Design Time** | 180 mins | 15 mins | **91% reduction** |
| **Automation Boilerplate** | 60 mins | 5 mins | **92% reduction** |
| **Edge Case Discovery** | Human-only | AI-assisted | **~40% more scenarios** |

The largest gain came not from speed—but from **breadth of risk coverage**.

---

## 🛠️ Technology Stack

- **Orchestration:** Node.js / Python  
- **LLM Layer:** OpenAI (GPT-4o), Gemini Pro  
- **Prompt Control:** LangChain  
- **Integration:** Jira REST API  
- **Automation Target:** Playwright (TypeScript)

All prompts and outputs are version-controlled and auditable.

---

## 🧠 Leadership Philosophy — *Augmentation, Not Replacement*

A critical success factor was addressing the **human side of AI adoption**.

- Ran enablement sessions to show:
  - AI removes repetitive, low-value work  
  - Humans retain ownership of risk, intent, and decisions  

- Repositioned manual testing as:
  **Creative exploration + AI-assisted acceleration**

The result:
- Increased team confidence  
- Reduced resistance to automation  
- Manual testers evolving into **AI-augmented Quality Engineers**

---

> **Outcome:**  
> GenAI became a force multiplier—not a threat—because it was implemented with governance, transparency, and respect for engineering judgement.
