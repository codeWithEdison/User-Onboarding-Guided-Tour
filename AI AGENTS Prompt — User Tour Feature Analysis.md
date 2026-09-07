Analyze the entire existing system and prepare a professional plan for implementing a **new-user guided tour/onboarding experience**.

### Important scope

The tour is ONLY for **normal user-facing actions and workflows**.

Do NOT include:
- Admin configuration
- System settings
- User management
- Role/permission management
- Organization configuration
- Technical configuration
- Developer/admin-only features
- Backend/internal processes

The goal is to help a newly registered/logged-in user understand **what they can do in the system and how to perform their important tasks**.

### What I want you to analyze

First inspect the entire existing application, including:

- Dashboard
- Navigation/sidebar
- User-facing modules
- Pages
- Buttons and actions
- Forms
- Workflows
- Request processes
- Asset-related actions
- Search/filter functionality
- Notifications
- Reports that normal users can access
- Profile/account features
- Any other functionality available to normal users

For each user-facing feature, determine:

1. What is the purpose of the feature?
2. Who uses it?
3. What important action can the user perform there?
4. Is it important enough to explain during onboarding?
5. What should the user learn from the tour?
6. What should be demonstrated interactively?
7. What should NOT be included because it is too advanced or unnecessary for onboarding?

### Identify the main user journeys

Do not simply list pages.

Identify the actual **user workflows**, for example:

Login
→ Dashboard
→ Find an asset
→ View asset details
→ Submit a request
→ Track request
→ Receive notification
→ Complete another action

For every important workflow, explain:

- Starting point
- Steps the user takes
- Important UI elements to highlight
- Expected result
- Whether it should be part of the first-time tour

### Role-based analysis

Identify the different NORMAL USER roles in the system and determine what actions are relevant to each role.

For example:

- Staff
- Requester
- Asset user
- Gatekeeper
- Driver
- Other non-admin roles already implemented in the system

Do not invent roles. Use the roles that actually exist in the codebase.

For each role, create:

**Role → Important actions → Recommended tour focus**

The tour should be different when necessary because users should only be guided through features relevant to their role.

### Recommend the onboarding structure

Based on your analysis, recommend:

#### 1. Welcome experience
What should a new user see immediately after their first login?

#### 2. Main guided tour
Recommend approximately 5–8 important steps.

#### 3. First-task guidance
Identify the most important action the user should actually perform after the tour.

#### 4. Getting Started checklist
Recommend actions that can be presented as a checklist rather than a tour.

#### 5. Contextual tips
Identify features that should be explained later when the user first encounters them instead of during the initial tour.

### Important principle

Do NOT try to explain the entire system in the first tour.

The goal is:

**"Help the user understand what they can do and successfully perform their first important task."**

Not:

**"Teach the user every feature in the system."**

### Required output

Produce a structured analysis with these sections:

1. **System User-Facing Feature Inventory**
2. **Normal User Roles**
3. **Important User Actions**
4. **Main User Journeys**
5. **Recommended Tour Focus**
6. **Role-Based Tour Recommendations**
7. **Getting Started Checklist**
8. **Contextual Tips**
9. **Features to Exclude From the Tour**
10. **Recommended Final Onboarding Flow**

Do NOT modify any code.

Do NOT implement the tour yet.

Do NOT create components yet.

First give me the analysis and recommended onboarding/tour structure based strictly on the existing system.