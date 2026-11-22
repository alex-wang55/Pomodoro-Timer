# Focus Flow

A single-page Pomodoro timer and task tracker. No build step, no dependencies — just open `index.html`.

**[Live demo](https://alex-wang55.github.io/Pomodoro-Timer/)**

## Features

- Focus / Short Break / Long Break timer cycle (25 / 5 / 15 min by default, adjustable)
- Task list — pick an active task and log completed pomodoros against it
- Automatic long break every 4th pomodoro
- Daily streak tracking
- Everything persists locally via `localStorage`
- Sound cue when a session ends
- Optional desktop notification when a session ends while you're in another window
- Stats: sessions and focus time today and over the last 7 days, a per-day chart, best streak and top tasks
- Light and dark themes (follows your system by default; switch in Settings)
- Keyboard shortcuts: `Space` start/pause, `R` reset, `S` skip, `1` `2` `3` modes, `N` new task, `?` show the list
- **Focus together**: create a room, send the link to a friend, and share one timer. Start, pause, reset, skip, mode and duration changes sync for everyone, and you can see who's in the room and what they're working on

## How Focus together works

Rooms use [Supabase Realtime](https://supabase.com/docs/guides/realtime) broadcast and presence channels. Nothing is stored server-side; the channel just relays messages between open tabs. The Supabase client loads only when you join a room, so the timer still works fully offline.

- Every action sends a full snapshot of the timer with the *time remaining* (not a wall-clock end time), so the two devices' clocks don't need to agree.
- Someone joining mid-session asks the room for the current timer and snaps to it.
- Tasks, pomodoro counts and streaks stay personal. When the shared timer finishes, each person gets credit locally.
- Anyone with the room link can join, so treat it like a meeting link.

## Running locally

Just open `index.html` in a browser, or serve the folder with any static file server:

```bash
python3 -m http.server 5173
```
