# Changelog

All notable changes to this project will be documented in this file.  
This format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and adheres to [Semantic Versioning](https://semver.org/).

---

## [1.6.0] - 2025-09-04

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
- Fixed **sorting issues** in task lists.

**Fixed**

- (Sorting bug is included in Changed/Improved above.)

## [1.5.0] - 2025-09-04

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
