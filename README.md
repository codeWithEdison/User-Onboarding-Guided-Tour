# User Onboarding / Tour Guide Prompts

These prompts are used to analyze and implement the **new-user guided tour** for the system.

## Prompt Order

Use the prompts in this order:

### 1. Analyze the System

Use the **Feature Analysis Prompt** first.

Purpose:

* Read and understand the existing system.
* Identify normal-user features and actions.
* Identify important user workflows.
* Determine what should be included in the tour.
* Determine what should be excluded.
* Create role-based tour recommendations.

**Do not implement anything at this stage.**

---

### 2. Implement the Tour

After the analysis is complete, use the **Implementation Prompt**.

Purpose:

* Read the previous analysis.
* Implement the professional guided tour.
* Focus only on normal-user actions.
* Create role-based tours where necessary.
* Add interactive highlights/tooltips.
* Add onboarding state persistence.
* Add first-task guidance and checklist where appropriate.
* Make the experience responsive and accessible.

The implementation should be based on the actual system, not a generic template.

---

## Important Rule

The onboarding should **not teach the entire system**.

Focus on:

> **What can this user do, and how can they successfully get started?**

Do NOT include:

* Admin features
* System configuration
* User management
* Permissions
* Technical settings
* Developer features

The final tour should be **short, useful, role-based, interactive, and professional**.

---

## Recommended Workflow

```text
Analyze Existing System
        ↓
Review Recommendations
        ↓
Implement Tour
        ↓
Test All User Roles
        ↓
Test Desktop + Mobile
        ↓
Fix Issues
        ↓
Final Review
```

**Do not start implementation before completing the analysis.**
