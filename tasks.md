# Tasks: Brain2Plan

Status key: `[x]` done, `[ ]` not started.

## Phase 1: Problem and design

- [x] Choose the track (Open Innovation) and the problem: unplanned, overloaded days
- [x] Define target users: students, professionals, freelancers
- [x] Write requirements (`requirements.md`)
- [x] Design the interface: notepad input on the left, time-blocked plan on the right

## Phase 2: Language understanding

- [x] Split input into tasks and strip bullets and numbering
- [x] Extract durations ("45 min", "2h", "1.5 hours", "half an hour")
- [x] Extract deadlines (today, tomorrow, weekdays, "in N days", "next week", clock times)
- [x] Classify task type and energy need
- [x] Estimate a default duration when none is given
- [x] Clean task titles for display

## Phase 3: Prioritization and scheduling

- [x] Score urgency and importance
- [x] Group tasks into Do now, Schedule, Quick win, Defer
- [x] Build the scheduler with energy-aware placement (sharpest hours)
- [x] Add lunch block, flex time before lunch, and breaks after 90 minutes of work
- [x] Detect overload and list tasks that did not fit
- [x] Warn when a task would finish after its stated time deadline
- [x] Generate a plain-language reason for each placement

## Phase 4: Interface and features

- [x] Settings: day start and end, sharpest hours, lunch time and length
- [x] Summary stats and capacity meter with realistic, tight, and overbooked verdicts
- [x] Task checklist with progress count
- [x] Focus timer with pause, resume, stop, and mark done
- [x] Copy plan, download Markdown, print
- [x] Copy unscheduled tasks as tomorrow's list
- [x] Save text and settings in the browser
- [x] Example loader and clear button
- [x] Keyboard shortcut (Ctrl/Cmd+Enter) to build

## Phase 5: Quality

- [x] Escape user text before display
- [x] Handle empty input and invalid day length with clear messages
- [x] Keyboard focus styles, labels, and screen-reader announcements
- [x] Respect reduced-motion settings
- [x] Responsive layout for phones
- [x] Print stylesheet
- [x] Smoke-test parsing and scheduling with the example input
- [ ] Test on real phones and in Safari and Firefox
- [ ] Try with five real to-do lists from friends and tune the keyword rules

## Phase 6: Submission

- [ ] Add team name and members to `readme.md`
- [ ] Create a GitHub repository and upload the four files
- [ ] Turn on GitHub Pages and confirm the live link works
- [ ] Take two or three screenshots for the submission form
- [ ] Record a short demo (load example, build plan, start focus timer, copy tomorrow's list)
- [ ] Submit on the Vedathon 2.0 portal

## Future work

- [ ] Optional LLM mode for messy or multilingual input
- [ ] Calendar import so meetings become fixed blocks
- [ ] Multi-day planning with automatic carry-over
- [ ] Learn real task durations from completed work
- [ ] Voice input and reminders
- [ ] Dark theme
