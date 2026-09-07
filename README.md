Create a professional `README.md` documentation for the **new-user onboarding / guided tour system** that you just implemented.

The README must document the implementation based on the **actual codebase**, not assumptions.

### README should include

# User Onboarding & Guided Tour

## 1. Overview

Explain:

* What the onboarding system does
* Why it exists
* Who it is designed for
* The difference between the initial guided tour, first-task guidance, checklist, and contextual tips

Make it clear that onboarding focuses on **normal user actions**, not administrative configuration.

---

## 2. Onboarding Flow

Document the complete flow:

```text
First Login
    ↓
Welcome
    ↓
Role-Based Tour
    ↓
First Important Action
    ↓
Getting Started Checklist
    ↓
Contextual Tips
```

Explain what happens at each stage.

---

## 3. Supported Roles

Document the actual normal-user roles supported by the implementation.

For each role explain:

* Role name
* Tour focus
* Important actions covered
* Any role-specific behavior

Do not document admin-only onboarding unless it actually exists.

---

## 4. Tour Steps

Create a table similar to:

| Step | Role  | Feature   | Target         | Purpose                  |
| ---- | ----- | --------- | -------------- | ------------------------ |
| 1    | Staff | Dashboard | Dashboard      | Introduce dashboard      |
| 2    | Staff | Assets    | Assets menu    | Explain asset access     |
| 3    | Staff | Requests  | Create Request | Explain request creation |
| ...  | ...   | ...       | ...            | ...                      |

Use the **actual implemented tour steps and selectors**.

---

## 5. File & Folder Structure

Explain where the onboarding implementation lives.

For example:

```text
src/
├── components/
│   └── onboarding/
├── hooks/
│   └── useOnboarding...
├── config/
│   └── onboarding...
├── pages/
└── ...
```

Do NOT invent paths.

Inspect the actual project and document the real structure.

For every important onboarding file explain:

* What it does
* Why it exists
* When a developer should modify it

---

## 6. How to Add a New Tour Step

Provide a practical step-by-step example based on the actual implementation.

Explain:

1. Where the tour configuration is stored.
2. How to define a new step.
3. How to identify the target element.
4. How to define the title and description.
5. How to assign the step to a role.
6. How to test the step.

Use actual code examples from the project's implementation.

---

## 7. How to Add a New Role Tour

Explain how a developer should add onboarding for a new normal-user role.

Include:

```text
Role
 ↓
Identify important user actions
 ↓
Create role-specific steps
 ↓
Register the tour
 ↓
Test the workflow
```

Explain exactly which files need to be modified.

---

## 8. Target Element / Selector Rules

Document how tour targets are identified.

If the implementation uses:

* IDs
* data attributes
* CSS selectors
* React refs
* component IDs

explain the actual approach.

Include recommended naming conventions.

For example, if appropriate:

```html
data-tour="asset-register"
```

Explain why stable selectors should be preferred over fragile selectors such as:

```css
div:nth-child(3)
```

---

## 9. Onboarding State

Document how the system knows whether a user has:

* Started the tour
* Completed the tour
* Skipped the tour
* Completed onboarding tasks
* Used a particular tour version

Document the actual database/API/local-storage/state implementation.

If there are database fields, provide the actual schema or relevant structure.

---

## 10. Tour Versioning

Explain how to update:

```text
tourVersion
```

and what happens when a new version is released.

Give an example of when developers should increment the version.

---

## 11. Restarting the Tour

Explain how users can restart the tour.

Document the actual UI entry point implemented for this functionality.

---

## 12. Getting Started Checklist

Explain:

* Where the checklist is implemented
* What tasks it tracks
* How completion is detected
* How to add a new checklist item
* When the checklist disappears or changes to a completed state

Use actual implementation details.

---

## 13. Contextual Tips

Document:

* Where contextual tips are defined
* How they are triggered
* How they are dismissed
* How developers can add a new contextual tip
* How to prevent tips from becoming intrusive

---

## 14. Responsive & Accessibility Behavior

Document how the onboarding behaves on:

* Desktop
* Tablet
* Mobile
* Keyboard navigation
* Screen readers
* Reduced motion

Only document behavior that is actually implemented.

---

## 15. Error Handling

Explain how the tour handles:

* Missing target elements
* Route changes
* Slow-loading pages
* Collapsed navigation
* Dynamic components
* User manually navigating
* Unexpected errors

---

## 16. Testing Guide

Provide a practical QA checklist.

### New User

* [ ] Welcome appears
* [ ] Correct role detected
* [ ] Correct tour starts
* [ ] Every target highlights correctly
* [ ] Navigation works
* [ ] Tour completes

### Existing User

* [ ] Completed tour does not repeatedly appear

### Skip

* [ ] User can skip
* [ ] Application remains usable
* [ ] Tour can be restarted if supported

### Mobile

* [ ] Tour works correctly
* [ ] Tooltip positioning works
* [ ] Navigation works

### Roles

* [ ] Each supported role receives the correct tour
* [ ] Admin-only functionality is not exposed

---

## 17. Development Workflow

Explain the recommended workflow for developers:

```text
Identify user action
        ↓
Add stable tour target
        ↓
Add/update tour configuration
        ↓
Test route navigation
        ↓
Test role behavior
        ↓
Test desktop/mobile
        ↓
Run lint/build/tests
        ↓
Deploy
```

---

## 18. Troubleshooting

Include common problems and solutions, such as:

* Tour step does not appear
* Target element cannot be found
* Tooltip appears in the wrong position
* Step appears before page loads
* Tour does not start
* Tour keeps appearing
* Role receives the wrong tour
* Mobile positioning issues

Base these troubleshooting instructions on the actual implementation.

---

## 19. Future Improvements

Suggest reasonable future improvements without implementing them, such as:

* Analytics for tour completion
* A/B testing onboarding
* More contextual guidance
* Localization
* Video onboarding
* Help center integration
* Onboarding analytics dashboard

Clearly separate implemented functionality from future ideas.

---

## Important documentation rules

* Document the **actual implementation**.
* Do not invent files, APIs, database fields, roles, or features.
* Use actual file paths from the repository.
* Use actual component/function names where useful.
* Include practical code examples where they help developers.
* Keep the documentation clear enough that another developer can maintain the onboarding system without asking the original developer.
* Explain both **how it works** and **how to modify it**.
* Clearly distinguish between **implemented**, **optional**, and **future** functionality.

Create/update the project's root:

```text
README.md
```

only if this onboarding documentation belongs in the root README.

Otherwise create:

```text
docs/ONBOARDING.md
```

Choose the location that best fits the existing project documentation structure.

Do not modify unrelated application code.
