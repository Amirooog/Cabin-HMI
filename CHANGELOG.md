# Cabin HMI — changelog

Version names: `LINE-MAJOR.MINOR.PATCH` (e.g. `TB-2.0.0`).

| Part | Meaning |
|---|---|
| **LINE** | Which prototype. `TB` Touch Baseline · `SK` Sliding Knob · `ST` Slide-anywhere Touch concept · `XP` experiments that never go to participants |
| **MAJOR** | Anything that changes a **task path**: where a control is, how many steps a task takes, what a control shows (label vs icon), gestures. **Trial data from different majors must not be pooled.** |
| **MINOR** | Visible change that leaves every task path intact: styling, new screens or options that are off by default, researcher tools. |
| **PATCH** | Bug fix. If a fix changes what a participant could do (e.g. a control that did not work), note it — trials run on the broken build for that task are invalid. |

Rules
- The build id is stamped into every trial and the CSV `build` column.
- Freeze a build before data collection starts: tag it `-field` in the notes below and change nothing until collection ends.
- Upload `index.html` + `sw.js` together; the id in both must match.

## TB-2.0.3 — 2026-09-20
- Installed app: manifest display standalone (with fullscreen preferred), page canvas painted in the app's own base colour so any strip the OS keeps outside the viewport is not black, diagnostic line in Settings (build, window size, screen size, measured insets).

## TB-2.0.2 — 2026-09-20
- Fix: installed app now fills the iPad screen. The safe-area insets are applied inside the screen (status row and bottom bar) instead of around it, with a fallback when iPadOS reports no insets, plus a manual Screen fit nudge in the researcher panel.
- Slightly larger type and dock on 11-inch and larger displays.

## TB-2.0.1 — 2026-09-20
- Fix: updates now reach the installed app on the first online launch (page fetched past the browser cache; the app checks for a new version each time it comes to the foreground and reloads itself, never during a running trial).

## TB-2.0.0 — 2026-09-20
- **Path changes:** temperature wheels on the Climate screen (swipe = 1 step; bar arrows unchanged). Airflow, defrost, heated-wheel and seat buttons are icon-only; seat heat and seat vent get distinct icons.
- Build id recorded per trial.

## TB-1.2.0 — 2026-09-20
- Scandinavian/frosted-glass restyle, Plus Jakarta Sans + Vazirmatn.
- Context modes Urban / Open road / Freeway / Carpool (colour, ambient light, motion, home layout). Mode locked during trials and logged. **Test in Urban** — other modes change home-screen paths.

## TB-1.1.1 — 2026-09-20
- Deep links per screen for Figma import.

## TB-1.1.0 — 2026-09-20
- Procedural city map, simulated driving, heading-up 3D guidance.
- Side-view car on Climate screen; confirmation toasts; screen motion.
- Researcher: Deep/Shallow layout switch (default Deep = unchanged paths), occlusion mode with TSOT logging.

## TB-1.0.1 — 2026-09-20
- Fix: seat heater could not be switched on. **T2 trials on TB-1.0.0 are invalid.**
- Share CSV from the installed app.

## TB-1.0.0 — 2026-09-20
- First touch-only baseline: Home, Climate, Media, Phone, Navigation, Settings; researcher mode with 11 timed tasks.
