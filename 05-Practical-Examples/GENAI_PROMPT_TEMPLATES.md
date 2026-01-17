# 🤖 GenAI Prompt Engineering Templates for QA

> **Purpose:** Provide reusable prompt templates for leveraging GenAI in test design, defect analysis, and data generation. Use these as starting points to accelerate and standardize GenAI-driven QA activities.

---

## 1. Test Scenario Generation

**Prompt:**
```
You are a senior QA engineer. Generate comprehensive test scenarios for the following feature:

Feature Description: [Paste user story or feature details here]

Requirements:
- Include 2-3 happy path scenarios
- Include 5-7 negative and edge cases
- Use Gherkin (Given/When/Then) format
- Highlight accessibility and security considerations
```

---

## 2. Defect Root Cause Analysis (RCA)

**Prompt:**
```
You are an expert QA analyst. Analyze the following defect report and suggest:
1. Root cause(s)
2. Suggested fix
3. Additional edge cases to test
4. Security implications

Defect Details:
[Paste defect summary, logs, and relevant code snippets]
```

---

## 3. Synthetic Test Data Generation

**Prompt:**
```
You are a QA automation engineer. Generate 10 realistic test data payloads for the following API:

API Schema/Fields: [Paste schema or field list]

Requirements:
- 5 valid payloads (covering edge cases)
- 5 invalid payloads (missing fields, wrong types, boundary violations)
- Output as JSON
```

---

## 4. Exploratory Testing Charter Suggestions

**Prompt:**
```
You are a QA lead. Suggest exploratory testing charters for the following feature:

Feature Description: [Paste feature details]

Requirements:
- Focus on user empathy, usability, and edge cases
- Include time-box and personas to use
```

---

## 5. Automation Code Boilerplate Generation

**Prompt:**
```
You are a test automation architect. Generate a boilerplate [Playwright/Selenium/Appium] test for the following scenario:

Scenario: [Paste Gherkin scenario or test case]

Requirements:
- Page Object aligned
- Clean, readable structure
- Parallel-safe
```

---

## 6. Automation Code Review

**Prompt:**
```
You are a senior automation engineer. Review the following test automation code for quality, maintainability, and best practices.

Code:
[Paste code snippet here]

Requirements:
- Identify code smells, anti-patterns, or flaky logic
- Suggest improvements for readability, reliability, and performance
- Check for adherence to framework standards (naming, structure, error handling)
- Recommend enhancements for reporting, logging, and parallel execution
```

---

## 7. Dependency & Vulnerability Analysis

**Prompt:**
```
You are a principal software architect with expertise in dependency management and security. Analyze the following dependency file and provide a detailed report.

Dependency File:
[pom.xml / package.json / build.gradle]

File Contents:
[Paste the full content of your dependency file here]

Report Requirements:
1. Outdated dependencies (current vs recommended versions)
2. Known vulnerabilities (severity + reference links)
3. Deprecated libraries and modern alternatives
4. High-level summary and top 3 priority actions
```

---

## 8. Automated Code Migration & Refactoring

**Prompt:**
```
You are a senior software engineer specializing in large-scale code migrations.

Migration Context:
- Library: [e.g., Rest-Assured]
- From Version: [e.g., 4.5.1]
- To Version: [e.g., 5.3.0]
- Key Breaking Changes:
  [e.g., "The given() method is now static", "JsonPathConfig has moved"]

Original Code:
[Paste the original Java/TypeScript/etc. code snippet here]

Tasks:
1. Refactor the code to be compatible with the new library version
2. Preserve original logic and behaviour
3. Add comments explaining what changed and why (reference breaking changes)
4. List additional improvements related to performance or best practices
```

---

*Tip: Always review and validate GenAI outputs before use in production. Human judgment is essential.*

*Last updated: January 2026*
