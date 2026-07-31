# AI Study Planner

A premium, offline-first study dashboard for students — built with **pure HTML5, CSS3 and vanilla JavaScript (ES6)**. No frameworks, no build step, no backend. Everything is stored in your browser's LocalStorage, so the whole app deploys as static files to GitHub Pages or Netlify in seconds.

---

## Project Overview

Students juggle subjects, deadlines and priorities across notebooks, chat groups and memory. **AI Study Planner** brings all of it into one glassmorphic dashboard and adds a rule-based scheduling engine that decides *what to study next* — scoring every pending task by priority, deadline proximity, overdue penalty and estimated effort. No external AI service is called; the intelligence is deterministic JavaScript you can read in `script.js`.

---

## Features

### Dashboard
- Time-aware greeting, live date and ticking clock
- Overall completion ring with animated progress
- Rotating daily motivational quote
- Today's tasks (including overdue) and upcoming deadlines
- Quick actions for every common workflow

### Subject Management
- Create, edit, delete and search subjects
- Assign a colour from a curated palette; the colour flows through tasks, calendar dots and charts
- Per-subject completion percentage and planned hours

### Task Management
- Fields: subject, title, description, deadline, priority, estimated study time, completion status
- Create, edit, delete, search, filter (subject / status / priority) and sort (deadline, priority, title, recency, duration)
- One-click completion with streak and study-history tracking

### AI Planner (simulated, fully offline)
- Detects overdue tasks and pushes them to the front
- Weights High priority work and imminent deadlines
- Builds a time-boxed schedule for today with automatic short breaks
- Suggests the number of 25-minute Pomodoro sessions per task
- Generates contextual coach tips based on your real workload

### Calendar
- Monday-first monthly grid with month navigation
- Today highlighting, per-subject deadline dots, overflow counters
- Click any day to inspect its tasks

### Progress Analytics
- Completion percentage, completed vs pending counts, total planned hours
- Weekly study-hours bar chart drawn on a `<canvas>` (retina-aware, theme-aware)
- Per-subject progress bars
- Daily streak counter

### Productivity
- Pomodoro timer with focus/break cycles, animated dial and tab-title countdown
- Live deadline countdowns in days/hours/minutes
- Daily goals for tasks completed and hours studied, with progress bars

### Settings
- Dark and light themes (persisted)
- Reduce-animations switch for accessibility
- Export JSON backup, import JSON backup (validated), clear all data
- Storage usage readout

### Extras
- Toast notifications
- Keyboard shortcuts (`N`, `S`, `/`, `T`, `G`, `P`, `Esc`)
- Animated loading screen and custom favicon
- Responsive navigation with mobile drawer
- Animated cards, empty-state illustrations, ARIA labels, focus-visible outlines
- Error handling around all storage and file operations
- Honours `prefers-reduced-motion`

---

## Screenshots

| Dashboard (dark) | Dashboard (light) |
| --- | --- |
| ![Dashboard dark](screenshots/dashboard-dark.png) | ![Dashboard light](screenshots/dashboard-light.png) |

| AI Planner | Analytics |
| --- | --- |
| ![Planner](screenshots/planner.png) | ![Analytics](screenshots/analytics.png) |

---

## Folder Structure

```text
AI-Study-Planner/
├── index.html          # Markup for every view, modals, SVG icon sprite
├── style.css           # Design tokens, glassmorphism, themes, responsive layout
├── script.js           # Store, Subjects, Tasks, Planner, Calendar, Analytics, Focus, Settings, UI
├── README.md
├── LICENSE
├── assets/
│   ├── logo.png
│   └── favicon.ico
└── screenshots/
```

---

## Installation

No dependencies and no build step.

```bash
git clone https://github.com/<your-username>/AI-Study-Planner.git
cd AI-Study-Planner
```

Then either open `index.html` directly in a browser, or serve it locally:

```bash
# Python
python3 -m http.server 8000

# or Node
npx serve .
```

Visit `http://localhost:8000`.

### Deploy

- **GitHub Pages** — push the repo, then Settings → Pages → Deploy from branch → `main` / root.
- **Netlify** — drag the folder onto the Netlify dashboard, or connect the repo with no build command and `.` as the publish directory.

---

## Usage

1. Open the app — demo subjects and tasks are seeded on first run so nothing is empty.
2. Go to **Subjects** and add your own papers, each with a colour.
3. Go to **Tasks** and add work with a deadline, priority and estimated hours.
4. Open **AI Planner** and hit *Regenerate plan* for today's schedule and Pomodoro suggestions.
5. Track deadlines in **Calendar**, momentum in **Analytics**, and run sessions from **Focus**.
6. Back up regularly with **Settings → Export JSON**.

### Keyboard shortcuts

| Key | Action |
| --- | --- |
| `N` | New task |
| `S` | New subject |
| `/` | Focus the search box |
| `T` | Toggle theme |
| `G` | Generate plan |
| `P` | Start / pause Pomodoro |
| `Esc` | Close dialog |

---

## Technologies

- **HTML5** — semantic sections, dialogs, inline SVG sprite
- **CSS3** — custom properties, grid, flexbox, `backdrop-filter`, keyframe animations, container-free responsive design
- **JavaScript (ES6)** — modules-by-closure, template literals, destructuring, `Intl` date/time formatting
- **Canvas 2D API** — weekly study-hours chart
- **LocalStorage** — versioned persistence with graceful corruption recovery

---

## Future Improvements

- Optional cloud sync and multi-device accounts
- Spaced-repetition flashcards per subject
- Recurring tasks and timetable import (`.ics`)
- Web Notifications for deadline reminders
- Offline PWA install with a service worker
- Drag-and-drop reordering of the daily schedule

---

## License

Released under the [MIT License](LICENSE).

---

## Author

Built as a portfolio project demonstrating clean front-end architecture, accessible UI engineering and heuristic scheduling logic without any external dependencies.
