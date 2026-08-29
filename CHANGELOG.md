# Changelog

All notable changes to this project will be documented in this file.  
This format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and adheres to [Semantic Versioning](https://semver.org/).

---

## [1.42.0] - 2026-08-30

🔑 **Key Update**: Introduced **MCP Server support**, token-based roadmap authorization, and team assignment for tasks.

**Added**

- Added **MCP Server** support for programmatic roadmap access and management.
- Added new **`assignedTeams`** field for assigning tasks to teams.
- Added **Deferred** and **Completed** banners to Task Cards for clearer closed-task status.
- Backend API now generates the available **Tags** and **Assignees** lists.

**Changed / Improved**

- Replaced sending the roadmap password with every request with **JWT-based authorization tokens**.
- **Hidden tasks** are no longer returned by the API when a roadmap is locked.
- Updated validation for **`nowDateSegments`** and **Phases** so an end date is no longer required when marked as completed.
- Improved Deck View Task Card performance by replacing the hover **scale effect** with a **yellow highlight ring**.

**Fixed**

- Fixed `phases.isCompleted` not being submitted to the backend.
- Fixed laggy Task Card interactions in **Deck View**.

## [1.41.0] - 2026-08-28

**Changed / Improved**

- Reduced **Timeline Badge** character limit to **16 characters**.
- Timeline task titles now automatically display on the **left side of the bar** when the bar is too short to show the title clearly.

**Fixed**

- Fixed **Today label** not remaining sticky when scrolling vertically in Timeline view.
- Fixed Task Card hover styling where scaling could cause the card borders to be clipped.
- Fixed **Duplicate Task** failing when `timelineBadge` is `null`.
- Fixed **Update Task** failing when `timelineBadge` is `null`.

## [1.40.0] - 2026-08-26

**Added**

- Added **Timeline Badge** to timeline task bars for additional task information.

**Changed / Improved**

- Updated the **Today line** to always appear in front of timeline bars.
- Added a **Today** label to the timeline for easier date reference.

## [1.39.0] - 2026-08-26

**Added**

- Added **assignee badge** to Timeline task bars for easier identification.
- Updated **History View** to use a **paginated List View** layout for improved navigation and readability.

## [1.38.0] - 2026-08-25

**Added**

- Enhanced the **Tips & Tricks** section on the Docs page with visualizations.
- Added a **bottom spacer** to the Timeline view so tasks at the bottom can be scrolled into a more comfortable viewing position.
- Added an explicit **`isCompleted`** field for phases instead of using `endDate` as the completion indicator.

**Changed / Improved**

- Enhanced **Timeline phase visualization**:
  - Added error state display for phases.
  - When grouping by **Assignee**, phases belonging to other assignees are now faded instead of hidden, providing better context.
- Updated phase completion logic to use the new **`isCompleted`** field.

## [1.37.0] - 2026-08-23

🔑 **Key Update**: Enhanced roadmap authorization, task visibility, and Timeline customization.

**Added**

- Added **Roadmap Status** with **Active** and **Unmaintained** states.
- Added **Roadmap Authorization** using an admin password.
- Added **Task Visibility Default** preference to customize the default visibility of newly created tasks.
- Added **Tips & Tricks** section to the Docs page.
- Added **task count by category** when opening the Category dialog.
- Added **right-click context menu** for tasks.
- Added **Timeline Size Stepper** to adjust the width and height of timeline bars.
- Added a **completed icon** for phases with an end date.

**Changed / Improved**

- Updated `document.title` dynamically based on the current page/roadmap for better identification when copying or pasting URLs.
- Improved scrolling behavior across different roadmap views.

**Fixed**

- Fixed Timeline warning icons overlapping with the grid when a task's target start date is a few days before today.
- Fixed Timeline phases not appearing for **NEXT** tasks.

## [1.36.0] - 2026-08-21

🔑 **Key Update**: Introduced planning phases with an expandable phase-based timeline.

**Added**

- Added **Phases** field for defining planning phases.
- Added **expandable phases** to the Timeline view.

**Changed / Improved**

- Timeline grid now dynamically expands to display **planning phases** and their associated tasks.

## [1.35.0] - 2026-07-11

🔑 **Key Update**: Introduced task pausing support and improved timeline and form visualization.

**Added**

- Added **`nowDateSegment`** to support pausing tasks.

**Changed / Improved**

- Updated **roadmap task form visualization** for better clarity and usability.
- Improved **timeline grid visualization** for more consistent layout.

**Fixed**

- Fixed security issue where users could **access tasks from another roadmap via URL manipulation**.

## [1.34.0] - 2026-06-20

**Changed / Improved**

- Made **header and footer action buttons** in Create/Edit Task form **sticky** for better usability.
- Updated **timeline visualization**:
  - Shows **warnings instead of error bars** for stale tasks.
  - _NEXT_ tasks with target start date < today are flagged as warnings.
  - _NOW_ tasks with future start dates are also flagged as warnings.

## [1.33.0] - 2026-09-04

🔑 **Key Update**: Introduced hidden tasks and improved filtering across views.

**Added**

- **`isHidden` task** feature.

**Fixed**

- Filtering by **category & assignee** now correctly shows the filtered grouping.
- Added **extra month buffer** for Timeline view.
- Bug with **`setUrlParams`** breaking links on Docs page fixed.

## [1.32.0] - 2026-08-04

🔑 **Key Update**: Improved task filtering and enhanced task creation/edit notifications.

**Changed / Improved**

- **Edit Task Form**: repositioned **Now/Next/Later toggle** for better UX.
- Enhanced **toast notifications** for creating/editing tasks: click on task ID to open the task.

**Fixed**

- Bug where **filtering was disabled** in **List, Deck, and Timeline views**.

## [1.31.0] - 2026-08-04

🔑 **Key Update**: Enhanced task filtering and improved List View interactions.

**Added**

- **Filter tasks** by **effective start and end date**.

**Changed / Improved**

- Change **Close & Reopen buttons** to **text buttons**.

**Fixed**

- Duplicated tasks are **no longer closed by default**.
- **Stop viewing modal** properly in List View.
- Ensure **section dropdown labels** are always ordered **NOW, NEXT, LATER**.

## [1.30.0] - 2026-04-04

🔑 **Key Update**: Introduced bulk editing, session password persistence, and enhanced list/timeline interactions.

**Added**

- **Bulk edit**: rename or remove **tags and assignees**.
- **Session password saving**: no need to unlock roadmap after navigating elsewhere.
- **Duplicate task** feature.
- **Routing timeline groups** (assignee, priority, tags) to List View with filters applied.
- **Edit and Delete buttons** in List View during edit mode for quick access.

**Changed / Improved**

- List View display updates:
  - **Category** moved to the front of each task row.
  - Show **Assessment Status label** as “Assessment” instead of “Status”.
- Fixed **Timeline start & end date calculation** bug.

**Removed**

- Dropped support for the **SQLite variant**.

## [1.29.0] - 2026-03-31

🔑 **Key Update**: Improved task selection, filtering, and timeline control.

**Added**

- Exact match filtering using `=` and `!=` for **tags, assignees, and categories**.
- **Selection box** for timeline bars when a task is selected.
- **Highlight bar** for list views when a task is selected.
- Option to view **closed/completed tasks** up to 100 years.
- Refactored: introduced `useFilteredRoadmapTasks` hook for task filtering logic.

**Changed / Improved**

- Removed **Category View**; clicking on a category now routes to **Timeline/List View**.
- Removed **Sort menu** from Deck View.

## [1.28.0] - 2026-03-27

🔑 **Key Update**: Enhanced filtering capabilities across Category and Timeline views.

**Added**

- **Task filtering** in Category View.
- **Filter by Assignee**.
- Timeline filter for **NOW, NEXT, or BOTH** tasks.

**Changed / Improved**

- Moved **Category View** from Experimental to **Planning group**.

## [1.27.0] - 2026-03-15

**Changed / Improved**

- Updated **Category View**: replaced the Completed group with an **Archive** group.
- Timeline improvements:
  - **Today’s line** now rendered behind task bars.
  - Error tasks default to **today’s date**.
  - Corrected sorting of timeline bars:
    - _NOW_ tasks use **Start Date**.
    - _NEXT_ tasks use **Target Start Date**.

**Fixed**

- Toast notifications for task creation now correctly indicate the task’s **NOW / NEXT / LATER** stage instead of always showing LATER.

## [1.26.0] - 2026-03-18

**Added**

- **Typeahead input suggestions** for assignees.
- **Confirm dialog** when deleting a category.

**Fixed**

- Typeahead suggestions now correctly filter when resetting.
- Timeline now properly shows tag suggestions.

## [1.25.0] - 2026-03-05

**Added**

- **Typeahead input** for tags to make it easier to search and select existing tags.

**Fixed**

- Timeline bars now correctly use the appropriate date for tasks in the **Next** stage (previously used Start Date).

## [1.24.0] - 2026-03-03

**Changed / Improved**

- **Negate Tag Filter**: Previously, tasks with multiple tags would disappear when one tag was negated. Now only tasks containing **only the negated tag** are hidden.
- Updated **Deck, List, and Timeline views** to properly hide tasks with the negated tag filter applied.
- Category form modal now indicates **text color** on top of the category label for better visibility.

**Fixed**

- Timeline column headers now handle **long category names** correctly, preventing overflow based on dynamic bar height and task card headers.

## [1.23.0] - 2026-02-27

**Changed / Improved**

- Task details now display dates in **dd MMM YY** format.
- **List view** enhancements:
  - Show **Start Date** for _NOW_ tasks, **Target Start Date** for _NEXT_ tasks, and **Completed Date** for completed tasks.
  - Sort tasks by **Column ID → Dates → Title** (previously only Column ID and Title).
- **History Release View** increased to show **25 items** instead of 5.
- Removed **Tracking View** and merged it into **Beta / Planning View**.
- Updated **History View** for better clarity and usability.
- Updated **Timeline View** visual to use play icon instead of clock3 icon.
- Updated **Deck View** visual to always expand the tasks on first load instead of collapsing them.

**Fixed**

- Timeline bars now end at **Completed Date** instead of today’s date.
- Fixed **scrolling issues** on the Docs page.
- Fixed **task error visualization** for List View.
- Fixed **completed task checkbox** should be on the right for **same day start & completed date**.
- Added validation for NOW tasks such that **completed date** cannot be earlier than **start date**.
- Added validation for NEXT tasks such that **target end date** cannot be earlier than **target start date**.

## [1.22.1] - 2026-01-16

**Changed / Improved**

- Updated **timeline error bars** to be more detailed and informative.

**Fixed**

- Able to delete roadmap with categories

## [1.22.0] - 2026-01-13

🔑 **Key Update**: Filter by whether task is completed

**Added**

- Added new filter by **completed** field.

## [1.21.1] - 2026-01-12

**Fixed**

- Timeline **group-by redirect**: now redirects to Category View when grouping by category (other groupings remain unchanged).
- Added **negate filter** option for Category and Tags.

## [1.21.0] - 2026-01-09

**Changed / Improved**

- Updated **timeline error bars** to be more detailed and informative.

## [1.20.0] - 2026-01-07

**Added**

- Allow in progress icon for NOW tasks in timeline view

**Fixed**

- timeline view should use today's date when target end date is earlier than today.

## [1.19.0] - 2025-11-17

**Added**

- Allow list view to show completed tasks.

**Changed**

- increase show completed tasks range option from 3 years to 5 years.

## [1.18.0] - 2025-11-15

🔑 **Key Update**: Group by Assignee,Tags,Priority

**Added**

- Added new **assignee** field.
- Added new **List view**.
- Added **group by Assignee, Tags, and Priority** (in addition to Category) for Deck, Timeline, and List views.

**Changed**

- Moved **Rank view** and **Board view** into Beta groups.

## [1.17.1] - 2025-10-31

**Fixed**

- Fix bug where timeline constantly resets to today's date after any action.
- Fix bug where tasks were not updated after updating or deleting categories.

## [1.17.0] - 2025-10-21

🔑 **Key Update**: Enhanced task cards with visual improvements.

**Added / Improved**

- **Gradient task bars** for better visual distinction.
- Added RoughTrack **logo**

## [1.16.0] - 2025-10-12

**Changed / Improved**

- **Collapsed/Expanded task state** in Board and Deck views now tracked separately.
- Updated **Add Task form** format for better usability.

**Fixed**

- URL state for Timeline view now correctly includes **taskId**.
- Fixed bugs with **Category inputs**.

## [1.15.0] - 2025-10-11

🔑 **Key Update**: Enhanced timeline editing and improved timeline display accuracy.

**Added**

- **Move Modal** for updating Start, Target Start, and Target End dates.
- Made **Priority Rationale** and **Request By** fields optional in task form.

**Fixed**

- Timeline bars not reaching the end of the month when months have more than 4 weeks.
- Timeline misalignment caused by horizontal scrollbars.
- Timeline header missing when no visible tasks are found after applying filters.

## [1.14.1 & 1.14.2] - 2025-10-13

- Minor bug fixes
- Clean up syling
- Clean up documentation

## [1.14.0] - 2025-10-10

🔑 **Key Update**: Added password reset support.

**Added**

- **Reset roadmap password** feature for easier admin recovery.

**Changed / Improved**

- Timeline now uses **start date** instead of _target start date_ when available.
- Removed **left border** from timeline task bars for a cleaner look.
- **Task menu** now always visible in preview mode (no longer requires hover).

## [1.13.0] - 2025-10-09

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
