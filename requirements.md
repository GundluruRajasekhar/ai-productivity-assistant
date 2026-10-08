# Requirements: Brain2Plan

AI productivity assistant for Vedathon 2.0 (Open Innovation track).

## 1. Problem statement

Most people start the day with a messy list in their head or in a notes app: unclear priorities, no time estimates, and far more work than the day can hold. They lose the first 30 to 60 minutes deciding what to do, tend to do easy tasks first, and end the day with the important work untouched. Existing to-do apps store tasks but do not decide, estimate, or warn about overload.

## 2. Goal

Turn an unstructured brain dump into a realistic, time-blocked plan for today in under a minute, and tell the user honestly when their list does not fit the day.

## 3. Target users

- Students juggling assignments, exams, and personal errands
- Working professionals with mixed deep work, emails, and meetings
- Freelancers and small business owners who plan their own day

## 4. Functional requirements

| ID | Requirement |
|----|-------------|
| FR-1 | The user can type or paste free-form tasks, one per line (semicolons also separate tasks). Bullets and list numbering are ignored. |
| FR-2 | The system extracts a duration from natural phrases ("45 min", "2h", "1.5 hours", "half an hour"). If none is given, it estimates one from the task type. |
| FR-3 | The system extracts a deadline from natural phrases ("today", "tomorrow", "by Friday", "in 3 days", "next week", "by 5pm"). |
| FR-4 | The system classifies each task by type (deep work, email, call, meeting, errand, health, general) and by energy need (high, medium, low). |
| FR-5 | The system scores urgency and importance and places each task in one of four groups: Do now, Schedule, Quick win, Defer. |
| FR-6 | The user can set day start, day end, lunch time and length, and whether they are sharpest in the morning or afternoon. |
| FR-7 | The system builds a time-blocked schedule that puts high-energy tasks in the user's sharpest hours, adds short breaks after long stretches of work, and reserves lunch. |
| FR-8 | Each scheduled task shows a plain-language reason for its position. |
| FR-9 | The system compares total work against available time and reports whether the day is realistic, tight, or overbooked. |
| FR-10 | Tasks that do not fit are listed separately, and the user can copy them as tomorrow's list. |
| FR-11 | The system warns when a task with a stated time deadline is scheduled to finish after it. |
| FR-12 | The user can tick tasks off and see progress. |
| FR-13 | The user can start a focus countdown for any task, with pause, resume, stop, and mark done. |
| FR-14 | The user can copy the plan, download it as a Markdown file, or print it. |
| FR-15 | The text and settings the user entered are remembered in the browser between visits. |

## 5. Non-functional requirements

| ID | Requirement |
|----|-------------|
| NFR-1 | **Privacy:** all processing happens in the browser. No task data is sent to any server. |
| NFR-2 | **Zero setup:** one static `index.html`, no build step, no account, no API key. |
| NFR-3 | **Performance:** a plan for up to 50 tasks renders in under one second on a typical laptop or phone. |
| NFR-4 | **Responsive:** usable on screens from 360 px wide up to desktop. |
| NFR-5 | **Accessible:** all controls have labels, keyboard focus is visible, status changes are announced, and motion is disabled for users who prefer reduced motion. |
| NFR-6 | **Resilient:** the app still works if browser storage or the clipboard is unavailable. |
| NFR-7 | **Safe output:** user text is escaped before display. |

## 6. Constraints and assumptions

- Language understanding is rule-based (keyword and pattern matching) rather than a large language model, so it works offline and costs nothing to run. Input is expected in English.
- The plan covers a single day. Multi-day planning is out of scope for this version.
- Time estimates for tasks without a stated duration are defaults, not predictions, and the interface says so.
- Weekday deadlines are resolved against the device's current date.

## 7. Out of scope (this version)

- Calendar integration and meeting import
- User accounts, sync across devices, and team sharing
- Voice input and notifications
- Language models for deeper understanding of messy input

## 8. Acceptance criteria

1. Loading the built-in example produces a schedule with at least one break, a lunch block, and a list of tasks that did not fit.
2. A task marked "urgent ... today" appears before low-impact tasks.
3. A deep-work task is placed inside the chosen sharpest hours when there is room.
4. An empty input shows a clear error and does not crash.
5. Reloading the page restores the previous text and settings.
6. No network request carries user task text.
