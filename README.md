# FlowPlanner

**Your day, in one place.**

FlowPlanner is a single-file, offline productivity suite that unifies **time, tasks, notes, habits, and email** — so you stop bouncing between a calendar, a to-do app, sticky notes, reminders, and Outlook.

No account. No install. No sync required. Open the HTML file and go.

![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-web-blue)
![Offline](https://img.shields.io/badge/offline-first-brightgreen)

## The problem

Most people plan with:

- a calendar for events
- a to-do app for tasks
- a notes app for ideas
- separate alarms and habits
- an email client that lives in a completely different world

None of these talk to each other. The day becomes fragmented, and the real questions stay unanswered:

- What should I do **next**?
- Do I have time for this?
- What did I forget?
- Which emails need action?

## What FlowPlanner does

### Planning

| Feature | Why it matters |
|--------|----------------|
| **Today dashboard** | Timeline + priorities + quick capture in one view |
| **Now / Do next** | Answers "what should I do right now?" |
| **Conflict detection** | Overlapping blocks are flagged before the day breaks |
| **To schedule pool** | Open tasks waiting to be placed on the clock |
| **Plan day** | One action places open tasks into free 30-min slots |
| **Tasks & projects** | Categories, priorities, progress bars |
| **Notes** | Fast capture + focus writing mode |
| **Calendar** | Month, week, and day views tied to the same date |
| **Habits** | Streaks that reset with the calendar day |
| **Daily summary & export** | Close the day, get a text backup with email inbox included |
| **Command palette** | `⌘/Ctrl+K` for power users |
| **Light / dark** | Respects system preference, toggleable |

### Email

| Feature | Why it matters |
|--------|----------------|
| **Offline inbox** | Inbox, Starred, Sent, Drafts, Scheduled, Trash — all in localStorage |
| **Composer** | Floating compose window with To, Cc, Subject, Body; minimise/restore |
| **Drafts** | Autosaves while you type — closing or hitting Esc never loses a draft in progress |
| **Attachments** | Drag-and-drop or pick files onto a message; stored as data URLs, 5MB/file cap, downloadable from the thread |
| **Send-later queue** | Pick a date/time; message parks in Scheduled and auto-sends on the minute |
| **Quick reply** | One-field reply bar inside any thread; always addressed to the right counterparty, even inside Sent |
| **Reply-all & Forward** | Real reply-all (includes every participant, never yourself) with proper quoting; reply-all stays in the same thread |
| **Thread view** | Collapsible older messages, thread count badge, auto-scrolls to latest |
| **Email → Task** | Convert any email subject into a FlowPlanner task in one click |
| **Star / Mark read / Mark unread** | Per-message, plus multi-select for bulk mark-read / star / delete |
| **Send with undo** | 5s undo window before a send is final, survives an accidental reload |
| **Delete with undo** | Moves to Trash with a 4.5-second undo window; permanent delete from Trash |
| **Empty Trash** | Bulk-empty via the undo toast when entering the Trash folder |
| **Contact autocomplete** | To/Cc suggest anyone you've already emailed |
| **Global search** | `/` search covers tasks, notes, events, and emails simultaneously |
| **mailto: mode** | Toggle in Settings → Compose opens your OS mail app instead |
| **Plug-in API** | `window.FPPlugins.register()` — ready for Gmail/Outlook/IMAP adapters |

Everything persists in **localStorage** across two keys: `flowplanner_v3` (planner) and `flowplanner_email_v1` (email). Your data never leaves the browser.

## Quick start

1. Download [`index.html`](./index.html)
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)
3. Choose **Start with sample day** or **Start blank**
4. Start planning and emailing — no signup

Optional: host the file on GitHub Pages, Netlify, or any static host.

## Keyboard shortcuts

### Global

| Key | Action |
|-----|--------|
| `1`–`5` | Switch views (Today → Habits) |
| `6` | Switch to Email |
| `N` | New task |
| `M` | Compose email (when on Email view) |
| `P` | Plan day |
| `F` | Focus mode |
| `/` | Search (tasks, notes, events, emails) |
| `⌘/Ctrl+K` | Command palette |
| `Esc` | Close modals / composer / folder drawer / exit focus |

### Email view (when a thread is open)

| Key | Action |
|-----|--------|
| `J` | Next message in folder |
| `K` | Previous message in folder |
| `R` | Focus the quick-reply bar |
| `E` | Mark read + close thread |
| `U` | Mark unread + close thread |

## Design principles

- **One continuous day** — time, tasks, notes, and email share the same surface
- **Zero friction** — open → type → schedule → send
- **Offline by default** — works without a network after load
- **Calm, high-end UI** — no clutter, no cinematic noise
- **Mobile parity** — bottom nav, FAB, folder drawer, and sheet menus for every desktop action

## Architecture

- Single HTML file (CSS + JS inlined, ~3,500 lines)
- No frameworks, no build step, no dependencies
- Inter font via Google Fonts (app still works offline after first cache)
- **Storage keys**
  - `flowplanner_v3` — planner data (tasks, events, notes, habits, projects, alarms)
  - `flowplanner_email_v1` — email data (messages, folders, settings)
- **Plug-in API** — `window.FPPlugins.register(name, adapter)` for Tier 3/4 email adapters (Gmail OAuth, Outlook Graph, IMAP/JMAP proxy)

## Email plug-in API

Third-party adapters can extend the email client without touching the core file:

```js
window.FPPlugins.register('my-adapter', {
  onLoad({ emailData, emailSave, renderEmailList, openCompose, toast, data, save }) {
    // inject real messages, hook compose Send, add folder buttons, etc.
  }
});
```

Planned plug-ins (not yet built):

| Tier | Adapter | Status |
|------|---------|--------|
| 3 | Gmail OAuth (Google API) | Planned |
| 3 | Outlook / Microsoft Graph | Planned |
| 4 | IMAP/JMAP proxy | Planned |

## Privacy

No analytics, no accounts, no servers. Data never leaves the browser unless you export it via **Export today** (`.txt`) or **Export all data + email** (`.json`) in Settings.

## License

MIT — use it, fork it, ship it.

---

Built to solve a real daily pain: **disconnected tools and an invisible day** — now with an email client better than Outlook, right inside your planner.
