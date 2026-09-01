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

## Running locally

Just open `index.html` in a browser, or serve the folder with any static file server:

```bash
python3 -m http.server 5173
```
