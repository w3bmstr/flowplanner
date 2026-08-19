# FlowPlanner

**Your day, in one place.**

FlowPlanner is a single-file, offline daily planner that unifies **time, tasks, notes, and habits** — so you stop bouncing between a calendar, a to-do app, sticky notes, and reminders.

No account. No install. No sync required. Open the HTML file and plan.

![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-web-blue)
![Offline](https://img.shields.io/badge/offline-first-brightgreen)

## The problem

Most people plan with:

- a calendar for events  
- a to-do app for tasks  
- a notes app for ideas  
- separate alarms and habits  

None of these talk to each other. The day becomes fragmented, and the real questions stay unanswered:

- What should I do **next**?  
- Do I have time for this?  
- What did I forget?  

## What FlowPlanner does

| Feature | Why it matters |
|--------|----------------|
| **Today dashboard** | Timeline + priorities + quick capture in one view |
| **Now / Do next** | Answers “what should I do right now?” |
| **Conflict detection** | Overlapping blocks are flagged before the day breaks |
| **To schedule pool** | Open tasks waiting to be placed on the clock |
| **Plan day** | One action places open tasks into free slots |
| **Tasks & projects** | Categories, priorities, progress |
| **Notes** | Fast capture + focus writing mode |
| **Calendar** | Month view tied to the same day |
| **Habits** | Streaks that reset with the calendar day |
| **Daily summary & export** | Close the day and take a text backup |
| **Command palette** | `⌘/Ctrl+K` for power users |
| **Light / dark** | Respects system preference |

Everything persists in **localStorage**. Your data stays on your device.

## Quick start

1. Download [`FlowPlanner.html`](./FlowPlanner.html)
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)
3. Start planning — no signup

Optional: host the file on GitHub Pages, Netlify, or any static host.

## Keyboard shortcuts

| Key | Action |
|-----|--------|
| `1`–`5` | Switch views (Today → Habits) |
| `N` | New task |
| `P` | Plan day |
| `F` | Focus mode |
| `/` | Search |
| `⌘/Ctrl+K` | Command palette |
| `Esc` | Close modals / exit focus |

## Design principles

- **One continuous day** — time, tasks, and notes share the same surface  
- **Zero friction** — open → type → schedule  
- **Offline by default** — works without a network after load  
- **Calm, high-end UI** — no clutter, no cinematic noise  
- **Mobile parity** — bottom nav + menu for every desktop action  

## Tech

- Single HTML file (CSS + JS inlined)  
- No frameworks, no build step  
- Inter font (Google Fonts; app still works if offline after first cache)  
- `localStorage` key: `flowplanner_v3`

## Privacy

No analytics, no accounts, no servers. Data never leaves the browser unless you export it.

## License

MIT — use it, fork it, ship it.

---

Built to solve a real daily pain: **disconnected tools and an invisible day.**
