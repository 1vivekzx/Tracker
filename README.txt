CBSE EXAM COMMAND CENTER 2027 — PWA & STUDY SUITE

FILES
- index.html: Complete offline-first app UI, dual exam countdowns, exam schedule, Science 50+15+Final roadmap, NCERT/Practice/Revision trackers, Daily Study Planner, Mock Test Tracker, Progress Dashboard, Native Android Widget Bridge & Settings
- manifest.webmanifest: Installable PWA metadata & app shortcuts
- sw.js: Offline cache service worker (v4)
- icon.svg: App icon
- README.txt: Setup and architecture guide

DEPLOY
1. Upload all files together to an HTTPS static host (Netlify, Vercel, GitHub Pages) or wrap in an Android TWA / WebView shell.
2. Open the HTTPS URL in Chrome on Android while online.
3. Wait for the page to load once; the service worker caches the app shell for full offline use.
4. Chrome menu > Install app / Add to Home screen.
5. Open app, choose Enable notifications, and allow notifications.

FEATURES INCLUDED
1. Complete Original Exam Command Center:
   - Live hero countdown for next upcoming exam, editable exam schedule, daily reminder scheduler (5:00 AM & 5:00 PM default + custom times in Settings), exam alert plan (7d, 3d, 1d, 1h before), offline/online status badge, and PWA install prompt.
2. Dual Live Exam Countdowns:
   - Dedicated live countdown cards for Mathematics (17 Feb 2027) and Science (22 Feb 2027) synced directly with your saved exam schedule.
3. Science Study Roadmap (50 + 15 + Final Revision):
   - Phase 1: 50 Days Syllabus Completion (editable start date, daily chapter pacing, phase milestones).
   - Phase 2: 15 Days Intensive Revision (subject-wise consolidation & weak-area drills).
   - Phase 3: Final Exam-Gap Revision (17 Feb – 22 Feb 2027 post-Maths high-yield sprint).
4. Official CBSE Class 10 Science Chapter-wise Tracker (13 NCERT Chapters):
   - Chemistry (4 chapters): Chemical Reactions and Equations; Acids, Bases and Salts; Metals and Non-metals; Carbon and its Compounds.
   - Biology (5 chapters): Life Processes; Control and Coordination; How do Organisms Reproduce?; Heredity; Our Environment.
   - Physics (4 chapters): Light – Reflection and Refraction; The Human Eye and the Colourful World; Electricity; Magnetic Effects of Electric Current.
   - Editable chapter targets (target dates, custom notes, priority High/Medium/Low) — no invented chapter weightages.
5. NCERT Granular Tracker:
   - Separate completion tracking per chapter for Theory Reading, In-Text Questions, and Back Exercises.
6. Practice Question Tracker:
   - Separate completion tracking per chapter for MCQs, Assertion-Reason, Case-Based Questions, Numericals (where applicable/editable), PYQs, and NCERT Exemplar.
7. Revision Tracker:
   - Multi-cycle revision tracking (Rev 1, Rev 2, Rev 3 / Final) per chapter with last-revised date logging.
8. Daily Study Planner:
   - Daily study hour & chapter targets, task checklist with subject/priority tags, focus timer / progress bar, and automatic rollover/history.
9. Mock Test & Sample Paper Tracker:
   - Log sample paper attempts, scores (out of 80 or custom max marks), time taken, mistake log / weak topics, and visual score trend chart.
10. Progress Dashboard & Offline Local Sync + Native Widget Bridge:
   - Real-time overall syllabus completion %, NCERT/Practice/Revision readiness, pending tasks, study statistics, JSON backup export/import, and `window.AndroidWidgetBridge` / `localStorage` widget payload sync (`cbseWidgetSummary2027`) for native Android WebView/TWA home-screen widgets.


=== UPDATE v4 (Nov 2026) ===
NEW IN THE APP
- Study Timer tab: Countdown (15/25/45/60/90 or custom minutes) and Stopwatch, per subject + topic note, pause/resume, saved sessions,
  today / last-7-days by subject. Time is added to the Daily Planner "Logged Hours". Survives app close (timestamp based).
  In the Android APK a live timer shows in the notification bar and an alert rings when the countdown ends.
- My Subjects: add/remove your own subjects (Settings). They show in Timer, Planner, Mock Tests and Chapters.
- Chapters: "+ Add chapter / subject", edit name/topics/subject/group, delete. Group chips are built from your chapters.
- Date sheet: add or remove exam papers (Settings), choose which 2 papers the home countdown cards show.
- Exam alerts (7d, 3d, 1d, 3h, 1h, 15min before every paper) are now scheduled on the phone for ALL your papers.

WIDGETS (APK)
1. Exam Countdown & Mission: days + live hours:minutes:seconds countdown (ticks every second), next paper, studied-today.
2. Pinned Papers: the two papers you pinned, each with days + live h:m:s.
3. Full Date Sheet: scrollable list of ALL papers you set (date, time, subject, days left / Done).
Widgets read your own schedule (no hard-coded dates) and refresh when you save changes in the app.

BUILD
- Put .github/workflows/build.yml and the update ZIP in your GitHub repo. The workflow unzips the ZIP into the repo, builds the APK
  and publishes it under Releases > "Exam Tracker APK (latest)".
- The APK is now signed with a fixed key, so every new APK installs over the previous one (your data is kept).
  FIRST TIME ONLY: the old APK was signed with a random key. Export a backup (JSON) first from the app, uninstall the old app,
  install the new APK, then Import the backup.

WIDGET UPDATE (v5)
- Widgets are resizable (long-press the widget on the home screen and drag the handles). Small sizes switch to a compact layout automatically.
- When the app opens (until you tap "Done"), it offers "Add widgets to home screen" so Android shows the add pop-up directly.
  Also in Settings > "Add widgets to home screen".
- Pin a subject per widget: when a widget is added (or long-press > Reconfigure) choose the paper for that widget:
  Exam Countdown = one paper (or Auto: next paper), Pinned Papers = two papers.
