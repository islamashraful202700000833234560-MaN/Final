# StudyFlow Final — v1.0

A mobile-first, multilingual, offline-first study planner for Android Chrome and modern browsers. Initial profile: Class 10 · SSC 2027 · Science · Bangladesh · NCTB. No official NCTB chapter list is prefilled; add or verify textbook details yourself.

## Languages
English, বাংলা, हिन्दी, 中文 (Simplified), Español, العربية, Français, Português, Русский, اردو. Arabic and Urdu use RTL document direction. Locale architecture is file-based under `locales/`. English is the default.

## Run locally
Service workers require HTTPS or localhost. In this directory run `python -m http.server 8000`, then open `http://localhost:8000`.

## Deploy to free GitHub Pages
1. Create a GitHub repository and upload the contents of this folder.
2. Repository → Settings → Pages.
3. Select Deploy from a branch, choose `main` and `/root`, then Save.
4. Wait for the HTTPS URL. Relative paths support repository subpaths.
5. Open the URL once while online to cache the app shell.

## Install on Android
Open the HTTPS GitHub Pages URL in Chrome → menu ⋮ → Install app or Add to Home screen. If install is not offered, use Add to Home screen. Open the installed app once online before relying on offline use.

## Offline and data
StudyFlow caches its app shell with a service worker and stores structured data in IndexedDB. Local data stays in this browser profile and does not automatically sync to another phone. Export JSON regularly. Browser storage can be cleared by Android/Chrome cleanup, so keep a backup somewhere safe. Restore validates the backup structure before replacing current data.

## Reminders: honest platform limits
The PWA reminder center requests browser notification permission only after the user taps Enable notifications. While the app page is running, it checks enabled reminders and can show notifications. A normal static PWA cannot guarantee exact-time alarms while fully closed, force-stopped, or restricted by Android battery management. This app does not claim otherwise. For guaranteed alarms, a separately developed native Android app would need Android AlarmManager/notification APIs and platform-appropriate exact-alarm permission handling. That native app is not included.

## Implemented
Responsive dashboard, daily planner, weekly/month calendar navigator, subject library, alarm center, reports and settings; add/edit/delete tasks; planned-time totals, overlap and over-capacity warnings; focus timer with pause/resume/reset and session recording; task completion/partial status and carryover suggestions; subject/book/chapter management; chapter status; ten language choices; light/dark/system theme; profile/goals; JSON backup/restore; IndexedDB persistence; PWA install metadata and offline app-shell cache. Reports can be printed/saved as PDF through the browser print dialog.

## Current limitations
- Notifications are best-effort while the app page is running; no reliable closed-app exact alarm.
- Alarm repeats are simple daily/weekdays/one-time reminders; advanced custom repeat rules, sound/vibration/snooze controls are not included.
- A focus session interrupted by browser termination is not guaranteed to recover.
- Calendar is a date navigator, not a drag-and-drop timetable editor.
- Subject/book/chapter data is user-maintained; no unverified official syllabus is invented.
- Locale files translate core navigation/common controls; longer helper copy in less common languages can fall back to English.
- No account, cloud sync, remote AI model or server.

## Privacy and security
No account or server is required. Study data is local to this browser profile. Imported JSON is size- and structure-validated, but only import files you trust. No API keys are shipped in frontend code.
