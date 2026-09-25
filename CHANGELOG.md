# Changelog

All notable changes to this project will be documented in this file.  
This format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and adheres to [Semantic Versioning](https://semver.org/).

---

## [2.9.0] - 2026-09-26

🔑 **Key Update**: Added **Backup & Restore**, enhanced Markdown editing, and improved Timeline date adjustments with phase synchronization.

**Added**

- Added **Backup & Restore** support for restoring roadmap data into a fresh database.
- Added a **Markdown Editor** with improved editing controls.
- Pasted URLs are now automatically converted into **Markdown links**.
- Added a **live overlay** when adjusting Timeline dates to preview changes to task dates and phases.

**Changed / Improved**

- `document.title` now includes the current **Roadmap View name** for easier identification of browser tabs and shared links.
- Timeline date adjustments now also update associated **Phase dates**, keeping phases synchronized with task date changes.

**Fixed**

- Fixed an authorization issue where administrators could still view protected content when **View as Admin** was disabled.

## [2.8.0] - 2026-09-25

🔑 **Key Update**: Improved task discovery and Backlog triage with **roadmap task search**, a new **Queued for Review** status, and enhanced Backlog grouping.

**Added**

- Added **Search Tasks** to quickly find tasks within a roadmap.
- Added **Add All** actions for **Assignees** and **Assigned Teams** in the Add/Edit Task form.
- Added a new **`QUEUED_FOR_REVIEW`** assessment status for backlog items that are ready to be reviewed.
- Added **flip-to-fit positioning** for overlay context menus to keep them within the visible viewport.

**Changed / Improved**

- Enhanced **Backlog View** with grouping by **Assessment Status** or **Category**:
  - When grouped by Assessment Status, tasks within each group are organized by Category.
  - When grouped by Category, tasks within each group are organized by Assessment Status.

**Fixed**

- Fixed Timeline task ordering not remaining sequential when **Group By** is applied.

## [2.7.0] - 2026-09-17

🔑 **Key Update**: Introduced **Quick Filters** for grouped views and **Category Archiving** for cleaner long-term roadmap management.

**Added**

- Added **Quick Filters** to grouped **Timeline** and **List** views for **Category**, **Tags**, **Assignee**, **Assigned Teams**, and **Priority**.
  - Open the group context menu to quickly filter by the selected group.
  - Include or exclude groups in a **staged filter** without immediately changing the current view.
  - Apply staged filters when ready, making it easier to build multi-group filters.

- Added **Category Archiving**, allowing categories to remain associated with existing tasks and history while being excluded from normal category selection.

**Changed / Improved**

- Made the **Deck View header sticky** so view controls remain accessible while scrolling.

**Fixed**

- Fixed the **Backlog** tag overflowing Task Cards in **List** and **Rank** views.

## [2.6.0] - 2026-09-14

🔑 **Key Update**: Improved roadmap preview and Timeline editing workflows with better organization and date snapping.

**Added**

- Added **Preview as Visitor** to preview a roadmap as it appears to non-members.
- Added a dedicated **Timeline Metadata** section to the Edit Task form, grouping **Timeline Badge**, **NOW Segments**, and **Phases**.
- Added a locked overlay to Timeline Metadata fields when the task is not in **NOW** or **NEXT**.

**Changed / Improved**

- **Backlog View** now shows all **LATER** tasks by default, including both backlog and confirmed LATER tasks.
- Timeline date adjustments now **snap to the start or end of the month** when using the Monthly Timeline View.

## [2.5.0] - 2026-09-12

🔑 **Key Update**: Introduced **roadmap visibility controls** and expanded Timeline navigation with **zoom** and **weekly views**.

**Added**

- Added **Public / Private Roadmap Visibility** to control whether roadmap content can be accessed by non-members.
- Added **Weekly Timeline View** as an alternative to the existing monthly view.
- Added **Delete User** functionality for administrators.
- Added dynamic `document.title` support for the **Generate Token**, **Docs**, and **Timeline Preview** pages.
- Added a floating **Table of Contents** to the Docs page for easier navigation.

**Changed / Improved**

- Re-implemented **Timeline Zoom** and removed the previous Timeline size stepper.
- Expanded the **Docs page** with additional information and guidance.
- Updated the **Move Task** action to support moving tasks to **LATER (Backlog)**.
- Improved transitions to **NOW**: when `startDate` is empty and `targetStartDate` exists, `targetStartDate` is automatically used as the task's start date.

**Fixed**

- Fixed **Assessment Status** not appearing when creating a new task.

## [2.4.0] - 2026-09-10

🔑 **Key Update**: Introduced a dedicated **Backlog workflow** for better management and assessment of LATER tasks.

**Added**

- Added **`isBacklog`** to distinguish backlog items within the **LATER** stage.
- Added a dedicated **Backlog View** for triaging and managing LATER tasks before they are ready for forward planning.

**Changed / Improved**

- Enhanced **Markdown** support with GitHub Flavored Markdown, including **strikethrough** and **task list checkboxes**.
- Improved **MCP tool descriptions** for task fields that support Markdown content.

## [2.3.0] - 2026-09-09

**Added**

- Added **Open**, **Completed**, and **Closed** task counts to the Category List dialog.
- Added **adjustable Timeline bars** for modifying task dates directly from the Timeline view.

**Changed / Improved**

- Improved the **Roadmap View toggle** UI for clearer navigation between views.
- Improved **toast notification** styling for better visibility.
- Updated the **selected Task Card and Timeline bar** highlight colors for clearer visual feedback.
- Updated text colors throughout the **Docs page** for better visual consistency.
- Restricted **admin authorization bypass** for MCP tool calls.

**Fixed**

- Fixed **Assigned Teams** labels on Timeline bars not being left-aligned correctly.

## [2.2.0] - 2026-09-03

**Added**

- Added additional logging for **MCP tool calls** and **API errors**.
- Added an environment flag to **disable health check request logging**.
- Added an environment flag to enable **pretty-printed logs** for improved readability.

**Changed / Improved**

- Updated the **Generate Token** page with a clearer workflow and more detailed descriptions.

**Fixed**

- Fixed the **search bar text color** in the Admin User List dialog.

## [2.1.0] - 2026-09-02

**Added**

- Added a clickable **Embed Link** to the share confirmation toast.
- Added additional application logging to improve visibility in **container logs**.

**Changed / Improved**

- **Unmaintained roadmaps** are now read-only and their tasks can no longer be edited.
- Updated the **Embed View** title banner to display the roadmap's **Unmaintained** status.
- Updated the **Timeline header width controls** to hide adjustment buttons when they are not applicable.

**Fixed**

- Fixed the **Generate Token** roadmap selector not updating when a roadmap is created, deleted, or changes between **Active** and **Unmaintained** status.
- Fixed task selection being lost after closing the Update Task dialog in **List**, **Rank**, and **History** views.

## [2.0.0] - 2026-09-02

🔑 **Key Update**: Replaced password-based roadmap access with **user authentication and roadmap membership**, introducing a new authorization model for RoughTrack.

**Added**

- Added **roadmap membership** for managing user access to roadmaps.
- Added support for two authentication modes:
  - **OIDC**, including integration with providers such as Keycloak.
  - **Trusted Header Authentication** using `X-User-Id`, `X-User-Name`, and `X-User-Role`.
- Added Embed URL support for displaying roadmaps within an `iframe`.

**Changed / Improved**

- Roadmap access and permissions are now determined by **user identity and membership** instead of a shared roadmap password.

**Removed**

- Removed **password-locked roadmaps** and the previous password-based authorization flow.
