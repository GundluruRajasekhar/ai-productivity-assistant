# Brain2Plan

**Write down everything on your mind. Get a realistic, time-blocked plan for today.**

Built for Vedathon 2.0, Open Innovation track: an AI productivity assistant that solves a real productivity problem.

## The problem

People start the day with a messy list and no plan. They are unsure what matters most, they guess how long things take, and they commit to far more than the day can hold. The result is wasted morning time, urgent work done late, and a feeling of falling behind. To-do apps store tasks, but they do not decide, estimate, or say "this will not fit".

## The solution

Brain2Plan reads a plain-text brain dump and does the planning for you:

1. **Understands** each line: duration, deadline, task type, and how much energy it needs.
2. **Prioritizes** with an urgent/important matrix: Do now, Schedule, Quick win, Defer.
3. **Schedules** the day: hard thinking goes into your sharpest hours, light tasks into lower-energy stretches, with breaks and lunch protected.
4. **Checks reality**: it compares your list against your working hours and tells you if the day is realistic, tight, or overbooked.
5. **Explains** every placement in one plain sentence, so you can trust or override it.
6. **Carries over** what does not fit: one click copies it as tomorrow's list.

## Features

- Free-form input: bullets, numbering, "45 min", "2h", "by Friday", "by 5pm", "tomorrow"
- Four-way priority with a reason shown on every task
- Energy-aware scheduling (morning or afternoon peak)
- Automatic breaks after 90 minutes of work, lunch block, flex time before lunch
- Overload detection with a list of tasks that did not fit
- Deadline warning when a task is scheduled to finish after its stated time
- Checklist progress and a built-in focus timer (pause, resume, mark done)
- Copy plan, download as Markdown, print
- Remembers your text and settings in the browser
- Private: nothing leaves your device

## Try it

Open `index.html` in any modern browser, then choose **Load an example** and watch the plan build. You can also press **Ctrl+Enter** (or **Cmd+Enter**) inside the text box to build.

Example input:

```
Finish quarterly report for my manager, due today, about 2 hours
reply to client emails 30 min
call mom
urgent: pay electricity bill today
prepare slides for Friday presentation - 90 min
gym 45 min
organize desk if time
```

## Run locally

No install or build is needed.

```
git clone <your-repo-url>
cd <your-repo>
# open index.html in your browser
```

Optional local server:

```
python -m http.server 8000
# visit http://localhost:8000
```

## Deploy on GitHub Pages

1. Put `index.html`, `readme.md`, `requirements.md`, and `tasks.md` in a GitHub repository.
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Your app will be live at `https://<username>.github.io/<repo>/` after a minute or two.

## How the "AI" works

Brain2Plan uses a rule-based language understanding engine that runs entirely in the browser. It is deliberately not a call to an external model, which keeps it instant, free, offline-capable, and private.

| Step | What it does |
|------|--------------|
| Parsing | Splits the dump into tasks and strips list markers |
| Duration extraction | Reads "1h 30m", "1.5 hours", "half an hour"; otherwise estimates from task type |
| Deadline extraction | Resolves "today", "tomorrow", weekdays, "in N days", "next week", and clock times against the current date |
| Classification | Matches task type (deep work, email, call, meeting, errand, health) and assigns an energy level |
| Scoring | Urgency comes from deadlines and urgent wording. Importance comes from stakeholders, money, health, deadlines, and people, minus low-stakes wording |
| Prioritizing | Urgent and important means Do now. Important only means Schedule. Urgent only means Quick win. Neither means Defer |
| Scheduling | Greedy time-line builder: at each step it picks the best-scoring task that fits, boosting deep work inside peak hours and light work outside them |

The language model is the natural next step: the parser is isolated in `parseTask()`, so it can be swapped for an LLM call that returns the same fields (title, duration, due date, category, urgency, importance).

## Tech stack

- HTML, CSS, and vanilla JavaScript in a single file
- Google Fonts (Bricolage Grotesque, IBM Plex Sans) with system fallbacks
- `localStorage` for saved text and settings

## Limitations

- English input only
- Plans one day at a time
- Estimates are defaults when you do not give a duration, and the app labels them as such
- Rule-based understanding can miss unusual phrasing; you can always edit the line and rebuild

## Roadmap

- Optional LLM mode for messier input and multiple languages
- Calendar import so existing meetings become fixed blocks
- Multi-day planning with automatic carry-over
- Learning your real task durations from completed work
- Voice input and reminders

## Project files

| File | Purpose |
|------|---------|
| `index.html` | The complete app |
| `requirements.md` | Problem, users, functional and non-functional requirements |
| `readme.md` | This document |
| `tasks.md` | Build checklist and future work |

## Team

Add your team name and members here before submitting.
