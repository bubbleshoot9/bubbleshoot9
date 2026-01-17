# 📝 Test Scenario Templates  
## Manual, Automation, and Gen AI-Enhanced Examples

---

## 🎯 Template 1: Manual Exploratory Testing

### Feature: User Account Recovery (High-Risk, Manual-First)

#### Context
**Business Impact:** 5/5 (Critical path)  
**Failure Risk:** 4/5 (Complex user flows)  
**Testing Approach:** Manual exploratory testing first; automate regression after validation

#### Exploratory Testing Charter
**Mission:** Explore account recovery flows to discover edge cases and usability issues that could frustrate users.

**Time-Box:** 90 minutes  
**Tester:** Senior QA (Level 3+)  

**Focus Areas:**
- User frustration points (error messages, recovery steps)
- Security edge cases (expired tokens, rate limiting)
- Cross-device/browser behavior inconsistencies

#### Manual Test Scenarios

**Scenario 1: Happy Path – Email Recovery**
```gherkin
Given the user has forgotten their password
When they click "Forgot Password"
And enter a valid registered email address
And click "Send Recovery Email"
Then they should receive an email within 2 minutes
And the email should contain a recovery link valid for 30 minutes
And clicking the link should allow password reset
And the new password should work for login
```

**Scenario 2: Edge Case – Expired Recovery Token**
```gherkin
Given the user received a password recovery email 31 minutes ago
When they click the recovery link
Then they should see "This link has expired" message
And the message should offer to resend the email
And the UI should remain accessible
```

**Scenario 3: Security – Multiple Recovery Attempts**
```gherkin
Given the user has requested 5 password resets in 10 minutes
When they attempt a 6th request
Then the system should show "Too many requests. Try again in 15 minutes"
And no new email should be sent
And the user's account should NOT be locked
```

**Exploratory Notes:**
- What happens if password reset occurs on mobile, then login attempt on desktop?
- Does the error message leak account existence?
- Can the user abandon and resume recovery?
- Accessibility: screen readers, keyboard-only navigation

---

## 🤖 Template 2: Automated Regression Testing

### Feature: Login Authentication (Low-Risk, Automation-First)

#### Context
**Business Impact:** 5/5  
**Failure Risk:** 1/5  
**Testing Approach:** Automate happy path + core negatives; manual spot-checks only

#### Playwright (TypeScript) Example

```typescript
import { test, expect } from '@playwright/test';

test.describe('Login Authentication - Regression Suite', () => {

  test('TC001: Valid login redirects to dashboard', async ({ page }) => {
    await page.goto('https://app.example.com/login');

    await page.fill('[data-testid="email"]', 'testuser@example.com');
    await page.fill('[data-testid="password"]', 'ValidPassword123!');
    await page.click('[data-testid="login-button"]');

    await expect(page).toHaveURL(/dashboard/);
    await expect(page.locator('[data-testid="welcome-message"]'))
      .toContainText('Welcome back');
  });

  test('TC002: Invalid credentials show error', async ({ page }) => {
    await page.goto('https://app.example.com/login');

    await page.fill('[data-testid="email"]', 'invalid@example.com');
    await page.fill('[data-testid="password"]', 'WrongPassword');
    await page.click('[data-testid="login-button"]');

    await expect(page.locator('[data-testid="error-message"]'))
      .toContainText('Invalid email or password');
  });

  test('TC003: Empty fields show validation errors', async ({ page }) => {
    await page.goto('https://app.example.com/login');
    await page.click('[data-testid="login-button"]');

    await expect(page.locator('[data-testid="email-error"]'))
      .toContainText('Email is required');
    await expect(page.locator('[data-testid="password-error"]'))
      .toContainText('Password is required');
  });

});
```

#### BDD (Cucumber + Java) Example

```gherkin
Feature: Login Authentication

  Background:
    Given the user is on the login page

  Scenario: Successful login
    When the user enters email "testuser@example.com"
    And the user enters password "ValidPassword123!"
    And clicks login
    Then the dashboard is displayed

  Scenario Outline: Invalid login attempts
    When the user enters email "<email>"
    And the user enters password "<password>"
    And clicks login
    Then an error message "<error>" is shown

    Examples:
      | email               | password       | error                     |
      | invalid@example.com | WrongPassword  | Invalid email or password |
```

---

## 🤖 Template 3: Gen AI-Enhanced Test Design

### Feature: Multi-Factor Authentication (MFA)

#### Prompt to LLM
```text
You are a senior QA engineer with expertise in security testing.

Generate MFA test scenarios considering:
- 6-digit SMS code
- 10-minute expiry
- 3 attempts max
- 15-minute lockout

Include happy paths, negative cases, edge cases,
and accessibility considerations.

Output in Gherkin format.
```

#### AI-Generated Scenario (Sample)

```gherkin
Scenario: Account locked after failed MFA attempts
  Given the user entered valid credentials
  And received an MFA code
  When the user enters an incorrect code 3 times
  Then the account is locked for 15 minutes
  And the user is notified
```

#### Human Review
- Accepted: core scenarios
- Modified: timing edge cases
- Added: SMS delivery failure scenario

```gherkin
Scenario: MFA SMS not received
  Given the user has not received the MFA code
  When they select "Resend code"
  Then an alternate delivery method is offered
  And the original code is invalidated
```

---

## 📊 Template 4: API Contract Testing

### Feature: User Profile API

#### Rest-Assured (Java)

```java
@Test
public void getProfile_validToken_returns200() {
    given()
        .header("Authorization", "Bearer " + token)
    .when()
        .get("/api/v1/users/profile")
    .then()
        .statusCode(200)
        .body("email", equalTo("testuser@example.com"));
}
```

#### Gen AI Test Data Prompt

```text
Generate 10 user profile JSON payloads:
- 5 valid (international names, long values)
- 5 invalid (missing fields, wrong formats)
```

#### AI Output (Sample)

```json
{
  "firstName": "María",
  "lastName": "García-López",
  "email": "maria@example.com"
}
```

---

## 🔑 Key Principles

### Manual Testing
- Focus on discovery, usability, and empathy
- Capture assumptions and gaps
- Validate messaging quality

### Automation
- Automate stable, high-frequency paths
- Keep tests fast and deterministic
- Use POM and data-driven approaches

### Gen AI
- Accelerate thinking, not decisions
- Review 100% of AI output
- Combine AI breadth with human context

---

**Philosophy:** Templates accelerate delivery.  
Judgment ensures quality.
