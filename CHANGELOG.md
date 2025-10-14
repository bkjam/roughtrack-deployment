# Changelog

All notable changes to this project will be documented in this file.  
This format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and adheres to [Semantic Versioning](https://semver.org/).

---

## [0.15.0] - 2025-10-11

🔑 **Key Update**: Enhanced timeline editing and improved timeline display accuracy.

**Added**

- **Move Modal** for updating Start, Target Start, and Target End dates.
- Made **Priority Rationale** and **Request By** fields optional in task form.

**Fixed**

- Timeline bars not reaching the end of the month when months have more than 4 weeks.
- Timeline misalignment caused by horizontal scrollbars.
- Timeline header missing when no visible tasks are found after applying filters.

## [0.14.1 & 0.14.2] - 2025-10-13

- Minor bug fixes
- Clean up syling
- Clean up documentation

## [0.14.0] - 2025-10-10

🔑 **Key Update**: Added password reset support.

**Added**

- **Reset roadmap password** feature for easier admin recovery.

**Changed / Improved**

- Timeline now uses **start date** instead of _target start date_ when available.
- Removed **left border** from timeline task bars for a cleaner look.
- **Task menu** now always visible in preview mode (no longer requires hover).

## [0.13.0] - 2025-10-09

🔑 **Key Update**: Major improvements to Timeline and Category views for better clarity and navigation.

**Added**

- More detailed **Category view**, showing unique details for _Now_, _Next_, _Later_, and _Completed_ tasks.
- **Delete** and **Close Task** buttons in View/Edit Task modal.
- Option to select **0–3 years** of completed tasks in Timeline view.

**Changed / Improved**

- Timeline bars now use **category colors** for better visual grouping.
- **View Task modal** replaced with a **side panel preview** in Timeline view.
- Timeline view updated with **more accurate bar lengths** and **adjustable month width**.

## [1.12.0] - 2025-10-07

🔑 **Key Update**: Enhanced category and timeline UX with better filtering, navigation, and task preview.

**Added**

- **React-Select** for searching through categories.
- Tags displayed on **Task Preview**.
- Close and Delete task options in **View Task modal**.

**Changed / Improved**

- Buttons updated to **icon buttons** for cleaner UI.
- Category view renamed to **Review View**.
- Color picker updated for category colors.
- Navigate from Timeline categories to **Review view**.

**Fixed**

- Category view scrolling bug.
- Rank view width not taking full space.
- Filtering Timeline now correctly filters completed tasks.

## [1.11.0] - 2025-10-06

🔑 **Key Update**: Improved task creation and visual feedback for incomplete tasks.

**Added**

- **Now / Next / Later** option in Create Task form.
- Validation **red highlight** for task cards with missing required fields.

**Changed / Improved**

- Roadmap **Delete** and **Edit** actions moved to **Settings button**.

**Fixed**

- Markdown rendering error in Task Card display.

## [1.10.0] - 2025-10-05

🔑 **Key Update**: Introduced **Task Categories** and enhanced **Timeline** and **Rank** views with richer filtering and grouping options.

**Added**

- **Task Categories** for better organization and grouping.
- **Closed completed tasks** now visible in Timeline view.
- **Filters** for Rank view.
- **Multi-value Tag & Category filters** for advanced filtering.
- **Group by Category** option in Timeline view.

**Changed / Improved**

- Enhanced **Task Modal inputs** for smoother editing and clarity.
- **Now / Next / Later** labels on task cards for clearer context.

## [1.9.0] - 2025-09-30

🔑 **Key Update**: Added **History Completed View** and improved Timeline and Deck UX for better task visibility and filtering.

**Added**

- **ALL filter** in Deck view for easier task filtering.
- New **History Completed View** to track finished tasks.
- **Resizable input fields** for Description, Priority Rationale, and Notes.

**Changed / Improved**

- Added **priority border** to task cards for a cleaner look.
- Timeline bars now display the **title in 2 lines** for more detail in a compact bar.

**Fixed**

- Styling issue with **Roadmap View Group dropdown**.
- **Rank View sorting** issue.

## [1.8.0] - 2025-09-27

🔑 **Key Update**: Introduced **Rank View** for easier prioritization.

**Added**

- Introduced **Rank View** – new workflow for updating and managing task priority.

**Changed / Improved**

- Grouped roadmap views:
  - **Planning** → Board, Deck, Rank
  - **Progress** → Timeline, History

**Fixed**

- Priority icon bug where **High** and **Critical** icons were swapped.

## [1.7.1] - 2025-09-20

**Added / Improved**

- **Edit button** in Task View modal for quick edits.
- Changed **collapsed/expanded button** in Board view from per-column to **global toggle**.
- Fixed **styling issues** with Timeline bars and History Timeline.
- Added **Move Task** option in task card dropdown menu.
- Added **Error Boundary** to handle unexpected crashes.

## [1.7.0] - 2025-09-18

🔑 **Key Update**: Introduced **Timeline View** for completed/closed tasks, making it easier to communicate progress to stakeholders.

**Added**

- **Vertical Timeline View** grouped by months for **completed/closed tasks**.

## [1.6.1] - 2025-09-13

**Added**

- **Reopen Task** feature in History table.

**Changed / Improved**

- Fixed **CSS styling** for Timeline View.
- Fixed **image aspect ratio** for Workflow Documentation page.

## [1.6.0] - 2025-09-11

🔑 **Key Update**: Introduced **Timeline View** for open tasks, making it easier to communicate upcoming roadmap plans to stakeholders.

**Added**

- Introduced **Timeline View** for visualizing tasks over time.
- Task titles are now clickable to **open task details**.
- Roadmap titles are now clickable to **open the roadmap**.
- Added **URL state support** for Docs page.

**Changed / Improved**

- Kanban now supports **global collapsed view**.
- Improved **React re-rendering performance**.
- Now/Next/Later columns can be **edited directly**.
- Replaced **Expected Window** with **Target Start Date** and **Target End Date** for tasks.

**Fixed**

- Fixed **sorting issues** in task lists.

## [1.5.0] - 2025-09-07

🔑 **Key Update**: Roadmap now supports **sharable links via URL state** for filters, views, and tasks.

**Added**

- Confirm **Delete Task** dialog to prevent accidental deletions.
- Confirm **Close Task** dialog for safer task management.
- Brought back **Compact View** option.

**Changed / Improved**

- Switched to **URL state** for:
  - Task filtering and sorting.
  - Deck view (Now, Next, Later).
  - Viewing a specific task.
  - Changing roadmap view (Board, Deck, History).
- Description and Priority Rationale on Task Cards are now line-clamped to 3 lines for better readability.

**Fixed**

- Issue Link button now hidden when no link is provided.
- Fixed bug where **Roadmap** and **Task** could not be deleted if subtasks existed.

## [1.4.0] - 2025-09-05

**Added**

- `managedBy` field to Roadmap model to indicate owner / manager.

**Changed / Improved**

- Restyled **Sort button** with clearer stacked layout.

## [1.3.0] - 2025-09-04

**Added**

- Sort button in Kanban header with visible sort field and direction.
- New assessment status: **Not Required**.
- Task card menu option to view full task details in a modal.

**Changed / Improved**

- Task cards now display full priority rationale and description (removed 3-line clamp).
- Removed the **Compacted View** option from task display.

**Fixed**

- Markdown bullets not rendering in task card descriptions.
- Frontend cache issue where updating a task card didn’t refresh the React Query c

## [1.2.0] - 2025-09-02

**Added**

- Total value displayed in table view for History Tasks and All Roadmaps pages.
- More detailed error messages for Task Cards.

**Changed / Improved**

- Cleaned up UI styling for gradient Task Cards.
- Expanded the default color palette for tag labels and progress status selection.

**Fixed**

- Navbar z-index issue that allowed scrolling over it.
- Webserver bug where subtasks were not returned in export & update endpoints.

## [1.1.1] – 2025-09-01

### Fixed

- **Subtasks API**: Fixed issue where API calls did not return subtasks.
- **Task Card Progress**: Fixed UI bug where the `progress` field failed to display previously created values, which could cause data loss when updating tasks.

## [1.1.0] – 2025-09-01

🔑 **Key Update**: Roadmap now supports **Markdown** for better readability

### Added

- **Documentation Page**: Explains how to use RoughTrack.
- **History View**: Review closed tasks (completed or dropped).
- **Deck View**: Glance at all task cards in a single layout.
- **Markdown Support**: Render markdown in `description`, `priority_rationale`, `notes`, and `subtasks` fields.
- **Custom Highlights**: Tags and progress fields now support customizable highlight colors.
- **Edit Roadmap Title**: Roadmap titles are now editable.
- **Filters**: Filter tasks by `assessment_status`, `priority`, `progress`, and `tags`.
- **SQLite Client**: Docker image updated to include SQLite database for easier local development.

### Changed

- **Renamed**: `status` field → `progress` field for clearer meaning.
- **Task Card Layout**: More compact spacing and reduced padding for better visibility when expanded.
- **SubTask Model**: Simplified to keep only `title` and `isCompleted` (removed `description` and `issueLink`).

### Fixed

- **Drag & Drop Stability**: Fixed crashes caused by excessive re-renders.

## [1.0.0] – First Prototype – 2025-08-27

### Added

- **Roadmaps View**: Create, view, and delete multiple roadmaps.
- **Export & Import**: Roadmaps can be saved and restored.
- **Password Lock**: Roadmaps are password-protected for privacy.
- **Board View**: Kanban-style drag-and-drop layout with _Now, Next, Later_ columns.
- **Infrastructure**: Initial database schema established (Prisma + PostgreSQL) for persistence.
- **Task Management**: Create, edit, and delete tasks within a roadmap.
- **Task Card Controls**: Expand, collapse, or compact tasks per column.
- **Task Card Details**: Cards support:
  - Tags
  - Description
  - Priority rationale
  - Priority
  - Issue link
  - Assessment status
  - Notes
  - Subtasks (title, description, issue links, completed flag)
  - Requester info (requested by, request date)
  - Timeline (expected window, start date, target date, completed date)
  - Status
