# HumbEE: Operational Clarity

HUMBEE — COMPLETE FRONTEND REBUILD
You are working on an existing application called HUMBEE.
I have uploaded the complete existing project folder directly to you.
There is NO GitHub connection to rely on.
The uploaded project files are the only source of truth for the existing implementation.
Your job is to completely redesign and rebuild the frontend/UI of this application while preserving the existing backend, database, business logic, workflows, authentication, calculations, and data behavior.
The current frontend was built earlier, but I do NOT want to preserve its visual design.
I want a completely new, premium, polished HUMBEE frontend built on top of the existing application.
1. VERY IMPORTANT — DO NOT START CODING IMMEDIATELY
First inspect the uploaded project completely.
Do not assume what the application does.
Do not invent functionality.
Do not remove functionality because it is not visible immediately.
Do not redesign based only on the screenshots or README.
Read the actual source code.
Start by understanding:
project structure
routes
pages
components
database layer
server actions
queries
TypeScript types
authentication
middleware
status logic
inventory logic
printing workflow
dispatch workflow
courier workflow
confirmation workflow
audit system
data lifecycle
existing reusable components
Also read these project documents if they exist:
VISION.md
PROJECT_STATUS.md
INVENTORY_DESIGN.md
INVENTORY_GO_LIVE.md
DATABASE_SCHEMA.md
WORKFLOW_TEST.md
design-review files
any other .md documentation describing product decisions
These documents describe decisions that must NOT be accidentally changed.
2. FIRST RESPONSE MUST BE AN AUDIT
Before changing code, give me a concise but complete audit containing:
A. Existing architecture
Explain:
framework
routing
data fetching
authentication
database connection
server/client component structure
reusable component structure
B. Existing screens
Identify every important route and what it currently does.
At minimum inspect:
Dashboard
Today
District View
Printer
Inventory
Courier
States
Events
Intake
Login
Also identify any unfinished or deprecated routes.
C. Existing workflows
Trace the actual code paths for:
Event
→ Printing
→ Count
→ Reprint
→ Material received
→ Inventory
→ Allocation
→ Dispatch
→ Courier
→ Delivery
→ Confirmation
D. Existing functionality
List important actions that already work.
DO NOT recreate them.
The new frontend should call the existing functionality.
E. Existing backend/data constraints
Tell me what must remain untouched.
F. Legacy UI
Identify which existing components/pages should be visually discarded and rebuilt.
Do NOT delete functionality simply because its old UI is being replaced.
3. THE MOST IMPORTANT RULE
This is a:
FRONTEND REBUILD
NOT:
backend rewrite
database redesign
workflow redesign
business-rule redesign
product-feature expansion
Do NOT change:
database schema
migrations
RLS
authentication
server actions
business calculations
inventory calculations
status engines
data relationships
API contracts
unless a frontend change absolutely requires a very small compatibility adjustment.
If you discover something missing from the backend:
STOP.
Tell me.
Do not silently invent a backend solution.
4. WHAT I WANT
I want the existing HUMBEE application to look like a completely new premium product.
The current frontend should be treated as legacy UI.
Do not copy its layout.
Do not copy its component hierarchy.
Do not simply change colors.
Do not simply add rounded cards.
Do not just "make it prettier".
Re-think the information hierarchy while preserving the existing workflow.
5. PRODUCT PHILOSOPHY
HUMBEE is an operational control system.
It manages the journey of event materials:
Event/District
→ Printing
→ Material received
→ Inventory
→ Allocation
→ Dispatch
→ Courier
→ Delivery
→ Receipt confirmation
The UI must make this journey obvious.
A new person should be able to use the application without asking:
"Ab kya karna hai?"
Every important screen should make the next action obvious.
6. PRIMARY USER
The main user is the person operating the daily workflow.
Their normal day is:
Today
→ find what needs attention
→ open district
→ perform next action
→ move material forward
→ repeat
Design for this person first.
Do not overload their interface with management/admin features.
Other users exist:
Admin
Manager
Intake/Data user
But their occasional tools should not dominate the operator workflow.
7. CORE DESIGN PRINCIPLE
Every screen must answer ONE primary question.
Dashboard
"What is happening across the operation?"
Today
"What should I work on now?"
District
"What is happening with this district and what is the next action?"
Printer
"Which districts need printing work?"
Inventory
"What material is available, what has been allocated, and what needs attention?"
Courier
"What is ready to dispatch and where is each shipment?"
States
"Where are the problems geographically?"
Events
"Which district/event am I looking for?"
Intake
"What new data is being imported?"
Never make every page into a dashboard.
8. VISUAL DIRECTION
The new UI must feel:
premium
mature
enterprise
calm
precise
operational
trustworthy
minimal
modern
It should NOT feel like:
generic SaaS template
admin dashboard template
CRM template
ERP template
flashy startup
analytics template
Bootstrap
generic shadcn
glassmorphism
neumorphism
Do not copy Linear, Stripe, Notion, Vercel or another product.
Use the quality level of premium products, but create a distinct HUMBEE identity.
9. COLOR SYSTEM
Use a restrained neutral palette.
Primary background:
#F6F5F2
Surface:
#FFFFFF
Border:
#E5E2DC
Primary text:
#1F1F1F
Secondary text:
#666666
Muted text:
#8A8A8A
Accent:
Honey amber.
Amber must be used sparingly.
Amber represents:
attention
delay
risk
action required
Do not create a rainbow status system.
Avoid:
bright green
bright red
excessive blue
purple
neon
gradients
glass effects
10. TYPOGRAPHY
Typography should create the hierarchy.
Use:
strong page titles
restrained section titles
clear labels
muted metadata
monospaced operational numbers where appropriate
Do not make every number enormous.
Only the most important number should dominate.
11. LAYOUT
Create a consistent application shell.
Desktop:
Sidebar
+
Main workspace
Use consistent:
content width
spacing
alignment
header structure
section spacing
Do not leave giant dead areas.
Do not squeeze everything into a narrow column.
The application should feel intentionally balanced.
12. SIDEBAR
Build a premium light sidebar.
Primary workflow:
Today
Dashboard
Printer
Inventory
Courier
Management/support areas:
States
Events
Intake
Reports, only if actually implemented
Do not show unfinished destinations.
Do not show Finance if it is still a stub.
Use the real HUMBEE logo from the uploaded project if available.
Do not replace it with a generic text logo.
13. DASHBOARD
Dashboard is an operational overview.
It should communicate the complete situation in roughly 10 seconds.
It should clearly tell a new person:
how many districts are involved
how many have received their coupons
how many are still being printed
how many are in courier
how many are at risk
where the biggest problems are
Use plain language.
Avoid jargon.
Example language:
"Of 117 districts — 21 delivered · 12 at risk"
is preferable to abstract terms such as:
"117 active · 21 confirmed · 12 critical"
because the first version explains the business meaning.
14. MATERIAL FLOW
The main material journey should be visually obvious:
At Printer → In Office → In Courier → Delivered
Use actual database values.
Do NOT hardcode example numbers.
Each stage must explain itself.
For example:
At Printer
70 districts
Being printed
In Office
3 districts
Ready for dispatch
In Courier
26 districts
On the way
Delivered
21 districts
Received
The user should understand where the coupons physically are.
15. NEEDS ATTENTION
Create a concise action-oriented area.
Examples:
Printing delayed
Print pending
Coupons short
Ready to dispatch
Courier stuck
Confirm receipt
Every item should communicate:
WHAT is wrong
+
WHICH district
+
WHAT should I do
Use one obvious action.
Do not create five competing buttons.
16. TODAY
Today is the operator's home.
This should be one of the most usable screens in the entire product.
It should answer:
"What do I need to do right now?"
Show:
urgent districts
deadline
current stage
problem
next action
Avoid management analytics here.
The operator should be able to start work immediately.
17. DISTRICT VIEW
District View is the core workflow screen.
It should tell one continuous story:
District identity
→ current situation
→ next action
→ material journey
→ reconciliation
→ inventory
→ dispatch
→ courier
→ receiver
→ activity
The next action should be visually dominant.
The journey should be easy to understand.
Avoid exposing backend terminology where business language is clearer.
18. STATE-DRIVEN ACTIONS
Actions must depend on actual state.
Examples:
Printing not counted:
Enter count
Short:
Order reprint
Reprint received:
Receive material
Material available:
Allocate
Ready:
Record dispatch
Shipment created:
Mark in transit
Then:
Mark out for delivery
Then:
Mark delivered
Then:
Confirm receipt
Do not show irrelevant actions.
The UI should guide the workflow.
19. PRINTER
Printer should answer:
"Which districts need printing work?"
Show:
district
required quantity
counted quantity
usable
short
reprint status
next action
Use the existing reconciliation logic.
Do not duplicate numbers unnecessarily.
Do not create a new printing system.
Do not change the existing business logic.
20. INVENTORY
Inventory is its own operational module.
Do NOT turn it into a second Dashboard.
There are two inventory models.
Coupons
Coupons remain district/event-specific.
Categories:
Influencer Coupons
Team Dalmia Coupons
Special Delegate Coupons
These are NOT one shared pool.
Shared materials
Lanyards
Pouches
These are shared pools.
Inventory should make it easy to understand:
received
allocated
remaining
dispatched where applicable
low stock
critical stock
reorder requirement
movement history
Primary actions:
Receive Stock
Allocate Stock
These should be visually obvious.
21. INVENTORY CORRECTIONS
Inventory history is an audit trail.
Do NOT silently overwrite history.
If someone enters:
50,000
instead of:
5,000
the original transaction must remain traceable.
The correction should be:
original
→ corrected
→ reason
Use the existing backend correction/audit system.
UI should make this understandable without making audit history dominate the screen.
Historical sections can be collapsed.
22. COURIER
Courier should answer:
"What needs dispatch and where is each shipment?"
First:
Ready to dispatch
Show districts where material is ready but dispatch has not been created.
Each should have:
Create dispatch
Then:
Consignments
Show the delivery journey:
Booked
→ In transit
→ Out for delivery
→ Delivered
Keep search and useful filters.
Rare edit/remove functionality should live under:
⋯
Do not clutter each row.
23. EVENTS
Events is a finder.
It should help users locate a district/event quickly.
Keep:
search
useful filters
district list
current stage
direct District View navigation
Do NOT recreate the old giant EventDrawer.
Do NOT duplicate:
Printer workflow
Inventory workflow
Courier workflow
District workflow
24. STATES
States is an overview/management lens.
Show:
state
affected districts
main issue
urgency
Do not make it another giant analytics dashboard.
25. INTAKE
Intake is the data entry/import area.
Workflow:
Upload
→ Review
→ Approve
Make validation obvious.
The user should understand:
what will be imported
what is invalid
what will change
before approval.
26. SEARCH
If the project already has global search/command functionality, make it discoverable.
Do not force users to know a keyboard shortcut.
Provide a visible search control.
Search should help find:
district
event
state
shipment
Do not expose dead destinations.
27. RARE ACTIONS
Do not remove working functionality just because it is rarely used.
Hide rare operations behind:
⋯
Examples:
Edit
Archive
Remove
Correction
Restore
The main screen should remain clean.
28. REAL DATA
This is extremely important.
Use the project's existing real data layer.
Never hardcode fake production values.
Do not create fake:
117 districts
21 delivered
70 printing
unless those values are actually returned by the application.
The UI must update automatically when the database changes.
If there is no live database connection available in the current environment:
do NOT fabricate data.
Use the project's existing loading/empty state.
29. DO NOT BREAK FUNCTIONALITY
Before replacing a component, determine:
who imports it
what server actions it calls
what data it receives
what routes depend on it
what state it manages
Preserve all important behavior.
The new frontend must remain connected to the existing backend.
30. SECURITY
Never expose:
service-role keys
private environment variables
database credentials
secrets
Do not bypass authentication.
Do not weaken middleware.
Do not move protected operations into insecure client-side code.
Preserve existing security architecture.
31. RESPONSIVE
Build desktop first, but properly support:
laptop
tablet
mobile
Do not simply shrink desktop.
On mobile:
navigation becomes compact
tables become stacked/scrollable appropriately
actions remain obvious
important status remains visible
forms remain usable
The core workflow must remain functional.
32. LOADING STATES
Every data-heavy page needs a polished loading state.
Use skeletons matching the actual layout.
Do not use giant generic spinners.
33. EMPTY STATES
Never show a confusing blank area.
Explain what is empty.
Example:
"No districts are waiting for dispatch."
not simply:
"0"
If an empty state has an obvious next action, show it.
34. ERROR STATES
Never expose technical errors to users.
Do not show:
SQL errors
stack traces
raw API errors
Show:
what happened
+
what the user can do
35. COMPONENT SYSTEM
Create a coherent reusable frontend component system.
Useful primitives may include:
Button
Card
SectionHeader
StatusChip
Metric
DataRow
Alert
EmptyState
PageHeader
Search
Filter
Modal
Timeline
JourneyRail
ReconciliationGauge
MaterialFlow
Do not create duplicate components with slightly different styling.
One visual language.
36. ANIMATION
Use subtle motion only when useful.
150–250ms.
Allowed:
fade
expand/collapse
status transition
save confirmation
Avoid:
bouncing
excessive scaling
decorative animation
parallax
flashy transitions
37. ACCESSIBILITY
Implement:
keyboard navigation
visible focus
semantic buttons
accessible forms
proper labels
readable contrast
modal focus handling
Do not communicate important information only through color.
38. UX LANGUAGE
Use plain business language.
Prefer:
Delivered
At Printer
In Office
In Courier
Printing delayed
Print pending
Coupons short
Ready to dispatch
Confirm receipt
Avoid unnecessary technical terminology.
A new user should understand the interface without a glossary.
39. NO DUPLICATE NUMBERS
Be extremely careful with numbers.
If a number appears multiple times, there must be a reason.
Do not show the same operational number repeatedly in:
hero
metric card
flow
list
unless each occurrence has a distinct purpose.
40. PREMIUM QUALITY TEST
For every screen ask:
If I remove this element, does the screen become worse?
If NO → remove it.
If an element is visually impressive but operationally useless:
remove it.
Premium does not mean more UI.
Premium means better decisions.
41. SCREEN-BY-SCREEN IMPLEMENTATION
Do not rebuild everything at once.
Implement in this order:
Global application shell
Dashboard
Today
District View
Printer
Inventory
Courier
States
Events
Intake
Login
Responsive pass
Accessibility pass
Final consistency pass
After each screen:
build
inspect
verify route
verify data
verify actions
verify navigation
check console
capture screenshot
42. SCREENSHOTS
For every completed screen create an actual screenshot.
Store them in:
design-review/
Use:
01-dashboard.png
02-today.png
03-district.png
04-printer.png
05-inventory.png
06-courier.png
07-states.png
08-events.png
09-intake.png
10-login.png
Screenshots must represent the real frontend.
Do NOT create fake mockup screenshots.
43. IMPORTANT — DO NOT CLAIM VERIFICATION WITHOUT ACTUALLY VERIFYING
If you cannot connect to the database:
say so.
If authentication blocks testing:
say so.
If a route cannot be tested:
say so.
Never claim:
"verified"
"production-ready"
"works"
unless you actually tested it.
44. FINAL WORKFLOW TEST
Once the UI is rebuilt, walk through the complete workflow using the existing application:
Event
→ Printing
→ Count
→ Reprint if needed
→ Material received
→ Inventory
→ Allocate
→ Dispatch
→ Courier
→ Delivered
→ Confirm receipt
At every step ask:
"Ab kya karna hai?"
The answer should be immediately visible.
If it is not:
fix the UI hierarchy.
Do not solve poor UX by adding more documentation.
45. FINAL CONSISTENCY TEST
Every screen must feel like the same product.
Check:
sidebar
typography
spacing
buttons
status chips
forms
tables
modals
alerts
empty states
loading states
action hierarchy
No screen should look like it came from a different application.
46. DO NOT PRESERVE THE OLD FRONTEND JUST BECAUSE IT EXISTS
The existing frontend is the implementation you are replacing.
Preserve:
FUNCTIONALITY
Replace:
VISUAL DESIGN
Improve:
INFORMATION HIERARCHY
Improve:
USABILITY
Improve:
RESPONSIVENESS
Improve:
ACCESSIBILITY
Improve:
CONSISTENCY
Do not simply reskin the existing pages.
47. DO NOT ADD FEATURES
This is a strict constraint.
Do not add:
CRM functionality
chat
AI assistant
analytics
notifications
new reports
new workflows
new database tables
unnecessary settings
unnecessary filters
unnecessary charts
Only improve the frontend of what already exists.
48. START NOW
Your first task is NOT to build the Dashboard.
Your first task is to inspect the uploaded project.
Read the files.
Understand the application.
Trace the existing workflows.
Then return the audit:
Architecture
Routes
Screens
Data sources
Existing actions
Existing workflows
Inventory architecture
Authentication/security
Legacy UI that should be replaced
Frontend rebuild plan
Do not modify the application before presenting this audit.
After I approve the audit, rebuild the frontend screen-by-screen.
The final result should look and feel like a completely new, premium HUMBEE product while retaining the existing working engine underneath.

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/5923fff6-86b4-4829-b46e-b427db22975b).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
