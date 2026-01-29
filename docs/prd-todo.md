# Product Requirements Document (PRD) - TODO App Upgrade: Due Dates, Priorities, Filters

## 1. Overview

We are upgrading the basic TODO app to support optional due dates, simple three-level priorities, and quick filters (All, Today, Overdue) so users can better organize tasks and focus on what matters today. Scope is intentionally lean to remain teachable and client-approved: storage stays local and there are no backend changes.

---

## 2. MVP Scope

- Due date: optional ISO `YYYY-MM-DD`; invalid values are ignored (treated as absent).
- Priority: enum "P1" | "P2" | "P3" with default "P3" when unspecified.
  - Accept only P1/P2/P3; other values are ignored.
  - UI provides a radio-like selector for P1/P2/P3; one selection at a time.
  - New tasks without an explicit priority are created as "P3".
- Filters: All, Today, Overdue.
  - Behavior: Today/Overdue views show only incomplete tasks; All may include completed tasks.
- Data model & validation: `title` is required; `priority` defaults to `"P3"`; `dueDate` optional ISO string.
- Constraints: Keep storage local only; no backend or external storage changes.

---

## 3. Post-MVP Scope

- Overdue tasks are visually highlighted to stand out.
- Advanced sorting order: overdue first → priority (P1→P3) → due date ascending → undated last.

---

## 4. Out of Scope

- Notifications.
- Recurring tasks.
- Multi-user functionality.
- Keyboard navigation.
- External storage (remain local only).
