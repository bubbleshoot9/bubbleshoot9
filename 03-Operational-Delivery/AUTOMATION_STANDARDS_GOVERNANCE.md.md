# 🛡️ Automation Governance & Engineering Standards

> **Purpose:** Establish a single, enforceable governance model for all automation frameworks—ensuring scalability, maintainability, and fast, reliable feedback across the organisation.

These standards apply to **all QA Engineers and Developers** contributing to automation code.  
Compliance is **mandatory** and enforced via automated checks, CI gates, and peer review.

---

## 🎯 1. Purpose & Scope

This document defines the **technical and operational standards** that govern how automation is designed, written, executed, and maintained.

Our objectives are to:
- Prevent framework sprawl and architectural drift  
- Ensure automation remains fast, stable, and trustworthy  
- Enable parallel execution at scale  
- Protect long-term ROI through maintainable code  

These standards apply across **web, mobile, and API automation stacks**.

---

## 🧱 2. Core Automation Standards (Non-Negotiable)

These principles apply to *all* frameworks and languages.

---

### 🔹 Test Isolation
- Every test must be **fully independent**
- Tests must not rely on shared state or execution order
- All created data, drivers, and contexts must be cleaned up
- Use test/scenario-level setup and teardown only

> If tests cannot run in parallel, they are not production-grade.

---

### 🔹 Clean Code & Maintainability
- Follow **SOLID** and **DRY** principles
- Use clear, intention-revealing names for classes and methods
- Remove dead code, unused imports, and commented logic
- Enforce formatting and linting standards (e.g. Prettier, Checkstyle)

---

### 🔹 Data Seeding & Management
- All test data must be externalised (JSON, Excel, ENV, config files)
- No hardcoded values in test logic
- Data loaders must be **thread-safe** and parallel-aware
- Prefer API-based data creation over UI where possible

---

### 🔹 Configuration & Environments
- Centralise all configuration (e.g. `test.config.ts`, `ConfigManager`)
- Secrets must be stored via environment variables—never in code
- Support multiple environments (dev / qa / prod) by default
- No environment-specific branching inside test logic

---

### 🔹 Reporting & Logging
- Use structured logging with test/scenario context
- Integrate with approved reporting tools (e.g. Allure, Extent)
- Automatically attach screenshots, logs, and traces on failure
- Logs must be actionable—not verbose noise

---

### 🔹 Parallelism & Thread Safety
- Use ThreadLocal or context-aware storage for:
  - Drivers
  - Test data
  - Loggers
  - Reports
- Shared utilities must be explicitly safe for parallel execution

---

### 🔹 Hooks & Lifecycle Management
- Use lifecycle hooks strictly for setup and teardown
- Business logic must never live in hooks
- Global hooks must be minimal and predictable
- Prefer framework-native lifecycle mechanisms (e.g. Playwright fixtures)

---

### 🔹 Error Handling & Diagnostics
- Catch and log exceptions with full execution context
- Fail fast and fail clearly
- Error messages must describe *what failed* and *why*

---

### 🔹 Reusable Utilities
- Core utilities (browser, data, reporting) must be modular
- No copy-paste across frameworks
- Shared logic belongs in shared libraries—not test classes

---

## 🧩 3. Stack-Specific Standards

The following sections define **additional requirements** per approved framework.

---

### 🧪 3.1 Playwright BDD Framework (Web | TypeScript)

- Use Playwright fixtures for browser, context, and page isolation
- Centralise browser lifecycle management (`BrowserManager.ts`)
- Use AsyncLocalStorage for per-test reporting and logging context
- All configuration lives in `test.config.ts` with ENV overrides
- Prefer strong TypeScript typing for models and test data
- Use Cucumber steps + Page Objects for BDD alignment

---

### 🌐 3.2 Web Browser Automation BDD Framework  
(Web | Java | Selenium)

- Use ThreadLocal for WebDriver and ExtentTest instances
- Hooks manage browser and reporting lifecycle only
- All Page Objects extend a shared base class
- Use PageFactory for element initialisation
- Externalise all config and test data (properties / Excel / JSON)
- Attach screenshots automatically on scenario failure

---

### 📱 3.3 Mobile Automation BDD Framework  
(Mobile | Java)

- ThreadLocal mandatory for drivers and reporting
- Centralised reporting via `ExtentReportManager`
- Retry logic managed via annotation transformers
- All mobile capabilities must be configurable
- Ensure parallel execution does not leak device state

---

### 🔌 3.4 API Automation Framework  
(API | Java)

- Thread-safe handling of config and secrets
- Centralised API client abstraction and logging
- Data-driven testing via external sources only
- Log full request/response payloads on failure
- Parallel execution must be stateless and isolated

---

## 🧭 Ownership & Governance

- This document is owned by the **Automation Lead**
- Reviewed and updated **quarterly**
- Any deviation requires explicit approval and documented justification

> Governance is not about control—it’s about enabling scale without chaos.
