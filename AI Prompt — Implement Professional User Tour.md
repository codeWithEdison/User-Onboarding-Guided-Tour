Using the **user-facing feature analysis and onboarding recommendations you just produced**, now implement a professional **new-user guided tour/onboarding experience** in the existing application.

### Core objective

Build a modern, professional onboarding experience that helps a new user understand the system and successfully perform their most important actions.

The tour must focus ONLY on **normal user actions and workflows**.

Do NOT include:
- Admin features
- System configuration
- User/role management
- Permission management
- Technical settings
- Developer features
- Backend/internal processes
- Any feature that normal users do not need to understand

### Before implementation

Review your previous analysis carefully and use it as the source for:

- Which features should be included
- Which features should be excluded
- Which roles need different tours
- Which workflows are most important
- Which actions should be demonstrated
- Which features should use contextual tips instead of the initial tour

Do not create a generic tour that is disconnected from the actual application.

---

## 1. Build a professional onboarding experience

Implement the following flow where appropriate:

**First login**
→ **Welcome**
→ **Role-based guided tour**
→ **First important action**
→ **Getting Started checklist**
→ **Contextual tips**

The experience should feel like a modern enterprise SaaS application.

It should be:

- Clean
- Modern
- Minimal
- Responsive
- Easy to understand
- Accessible
- Non-intrusive
- Fast
- Consistent with the existing application design

Do not overwhelm users with too many steps.

---

## 2. Role-based tours

Use the roles that actually exist in the application.

Do NOT invent roles.

For each relevant normal-user role, show only the features and actions that are relevant to that role.

For example:

```text
Staff
→ Dashboard
→ Relevant assets
→ Create request
→ Track request
→ Notifications

Gatekeeper
→ Gate operations
→ QR scanning
→ Verification
→ Relevant records

Driver
→ Assigned activities
→ Vehicle-related actions
→ Required submissions
```

These are only examples. Use the actual roles and workflows discovered in the codebase.

If two roles have substantially different workflows, their onboarding should be different.

---

## 3. Interactive guided tour

Implement real UI highlighting rather than a sequence of generic modal dialogs.

The tour should support:

- Spotlight/highlight around the target element
- Tooltip/popover
- Step title
- Short explanation
- Previous
- Next
- Skip
- Finish
- Step progress
- Automatic positioning
- Responsive behavior
- Proper handling when the target element is not immediately visible

Example:

```text
        ┌──────────────────────────────┐
        │ Assets                       │
        └──────────────────────────────┘
                 ▲
          highlighted element

┌───────────────────────────────────────┐
│ Assets                                │
│ View and manage the assets available  │
│ to you.                               │
│                                       │
│ Step 2 of 6          [Back] [Next →] │
└───────────────────────────────────────┘
```

Use an established tour library if one already exists in the project.

If there is no suitable existing implementation, use an appropriate production-ready library such as **Driver.js, React Joyride, or Shepherd.js**, choosing the option that best fits the existing stack.

Do not introduce unnecessary dependencies if the project already has an appropriate solution.

---

## 4. Do not break existing navigation

The tour must work correctly with the existing application routing.

If a tour step requires another page:

```text
Tour Step
↓
Navigate to required page
↓
Wait for page/component to render
↓
Find target element
↓
Show spotlight
↓
Continue tour
```

Do not use fragile arbitrary timeouts where they can be avoided.

Handle:

- Route changes
- Lazy-loaded components
- Dynamic content
- Collapsed sidebar
- Mobile navigation
- Missing elements
- Different screen sizes

If a target element does not exist, gracefully skip that step instead of breaking the tour.

---

## 5. First-task guidance

The onboarding should not stop after explaining the UI.

Identify the most important first action for each normal-user role from your previous analysis.

Where appropriate, guide the user toward actually completing that action.

For example:

```text
Tour completed 🎉

You're ready to get started.

[Complete Your First Request]
```

The action should be based on the real application workflow.

---

## 6. Getting Started checklist

Where appropriate, implement a small onboarding checklist on the dashboard.

Example:

```text
Getting Started

✓ Explore your dashboard
✓ Complete your profile
○ Submit your first request
○ Track your request

3 of 4 completed
██████████████░░
```

The checklist must reflect real user actions in the application.

Do not add fake tasks simply to fill the checklist.

Once the onboarding tasks are completed, the checklist can automatically disappear or show a completion state.

---

## 7. Persist onboarding state

Do not show the full tour every time the user logs in.

Persist the user's onboarding state using the existing backend/user architecture.

At minimum, support:

```text
tourStarted
tourCompleted
tourSkipped
tourVersion
currentStep
completedAt
```

Use the existing authentication/user infrastructure where possible.

Do not create duplicate user systems or unnecessary database structures.

If a database migration is required, design it consistently with the project's existing database architecture.

---

## 8. Tour versioning

The onboarding must support future updates.

For example:

```text
tourVersion = "1.0"
```

If the application receives a significantly updated onboarding experience later, the system should be able to recognize:

```text
User completed version 1.0
Current version = 2.0
```

and optionally show the updated tour.

Do not force existing users to repeatedly see the same onboarding unnecessarily.

---

## 9. Skip and restart

Users must be able to:

- Skip the tour
- Finish the tour
- Continue later where appropriate
- Restart the tour from Help/Profile if supported by the existing UX

Add a professional entry point such as:

```text
Help
→ Take Product Tour
```

or an equivalent location that fits the existing application.

---

## 10. Contextual guidance

Do not put everything into the initial tour.

For features that are too advanced or only useful when the user reaches a specific page, implement contextual tips where appropriate.

Example:

```text
💡 Tip

You can export this report to Excel
using the Export button.

[Got it]
```

Keep contextual guidance minimal and useful.

Avoid creating annoying popups.

---

## 11. Design requirements

Follow the application's existing:

- Colors
- Typography
- Spacing
- Buttons
- Icons
- Border radius
- Shadows
- Dark/light mode
- Responsive design

The onboarding should feel like it is **part of the application**, not a third-party feature pasted on top.

Use professional microcopy.

Keep explanations short.

Avoid technical language.

---

## 12. Accessibility

Make the onboarding accessible.

Support:

- Keyboard navigation
- Focus management
- Screen readers where practical
- Sufficient contrast
- Escape/close behavior
- Mobile/touch interaction
- Reduced-motion preferences where practical

Do not trap the user in the tour.

---

## 13. Error handling

The tour must never prevent the user from using the application.

If:

- A target element is missing
- A page fails to load
- A route changes unexpectedly
- A component is unavailable
- The user navigates manually
- The sidebar is collapsed
- The screen size changes

the application must continue working normally.

The tour should gracefully recover, skip the affected step, or allow the user to exit.

---

## 14. Implementation quality

Before writing code:

1. Inspect the existing onboarding-related code, if any.
2. Inspect routing.
3. Inspect authentication/user state.
4. Inspect the existing role/permission structure.
5. Inspect the components that will be targeted by the tour.
6. Re-read your previous feature analysis.
7. Select the final tour steps based on the actual application.

Then implement the feature using the existing project architecture and conventions.

Avoid unnecessary refactoring.

Do not rewrite unrelated parts of the application.

Do not break existing functionality.

---

## 15. Testing

After implementation, verify:

### New user
- Welcome screen appears
- Correct role-based tour starts
- Steps point to the correct UI elements
- Navigation works
- Tour completes correctly

### Existing user
- Completed tour does not repeatedly appear

### Skipped user
- Tour can be skipped
- User can restart it later if implemented

### Different roles
- Each role receives the appropriate user-facing tour

### Responsive
- Desktop works
- Tablet works
- Mobile works

### Edge cases
- Missing target element
- Route change
- Collapsed sidebar
- Slow page loading
- User manually navigating during the tour

### Regression
- Existing application functionality remains unchanged

---

## Important constraints

**Do not implement admin onboarding.**

**Do not expose admin-only features in normal-user tours.**

**Do not create a huge 20–30 step tour.**

**Do not explain every page.**

Focus on the user's actual workflows and important actions.

The final experience should answer:

> **"I am a new user. What can I do here, and how do I get started?"**

### Final deliverables

After implementation:

1. Summarize what was implemented.
2. List the tour steps for each normal-user role.
3. List the features intentionally excluded from onboarding.
4. List any new dependencies.
5. List any database/API changes.
6. Explain how onboarding state is persisted.
7. Report any issues or limitations.
8. Run the project's available tests/build/lint checks and fix relevant errors.

Do not stop at analysis. **Implement the complete feature now.**