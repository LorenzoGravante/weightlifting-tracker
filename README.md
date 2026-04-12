# Strength + CrossFit Tracker — User Guide

A mobile-first progressive overload tracker built around block periodization. The app runs entirely in the browser with no installation required, and all data is stored locally on your device.

---

## Table of Contents

1. [Adding the App to Your Home Screen](#1-adding-the-app-to-your-home-screen)
2. [First Launch — Setting Your Baseline 1RM](#2-first-launch--setting-your-baseline-1rm)
3. [Understanding the Programme Structure](#3-understanding-the-programme-structure)
4. [Navigating the App Tabs](#4-navigating-the-app-tabs)
   - [SCHEDULE](#schedule)
   - [HISTORY](#history)
   - [PROGRESS](#progress)
   - [SOURCE](#source)
   - [SETTINGS](#settings)
5. [Logging a Session](#5-logging-a-session)
6. [The CrossFit Yesterday Toggle](#6-the-crossfit-yesterday-toggle)
7. [Understanding Weight Calculation Logic](#7-understanding-weight-calculation-logic)
8. [The Rest Timer](#8-the-rest-timer)
9. [RPE — Rate of Perceived Exertion](#9-rpe--rate-of-perceived-exertion)
10. [Personal Records (PRs)](#10-personal-records-prs)
11. [Deload Weeks](#11-deload-weeks)
12. [Exporting and Importing Data](#12-exporting-and-importing-data)
13. [Starting Cycle 2 — Restarting the Programme](#13-starting-cycle-2--restarting-the-programme)

---

## 1. Adding the App to Your Home Screen

The app is a single HTML file designed to behave like a native mobile app. For the best experience, save it as a shortcut on your phone's home screen so it launches full-screen without browser chrome.

**On iPhone (Safari):**
1. Open the HTML file in **Safari** (not Chrome or Firefox).
2. Tap the **Share** button (box with arrow pointing up) at the bottom of the screen.
3. Scroll down and tap **"Add to Home Screen"**.
4. Name it **"Strength + CF"** and tap **Add**.
5. The app icon will appear on your home screen and open full-screen.

**On Android (Chrome):**
1. Open the HTML file in **Chrome**.
2. Tap the **three-dot menu** (⋮) in the top-right corner.
3. Tap **"Add to Home screen"** or **"Install app"**.
4. Confirm by tapping **Add**.

> ⚠️ **Important:** All data is saved in the browser's `localStorage` tied to the file's location. Always open the app from the same browser and the same saved file. Clearing browser data or switching browsers will erase your logs.

---

## 2. First Launch — Setting Your Baseline 1RM

**Everything in this app flows from your baseline 1-Rep Maximum (1RM).** This is the single most critical setup step — every working weight across all 12 weeks is automatically calculated as a percentage of these values. Inaccurate 1RMs will produce incorrect prescriptions throughout the entire cycle.

Navigate to the **SETTINGS** tab immediately on first launch.

### Exercises and defaults

| Exercise | Default 1RM | Increment |
|---|---|---|
| Power Clean | 70 kg | 1.25 kg |
| Back Squat | 120 kg | 2.5 kg |
| Deadlift | 160 kg | 2.5 kg |
| Military Press | 50 kg | 0.75 kg |
| Bench Press | 80 kg | 2.5 kg |
| Weighted Pull-ups | 20 kg | 1.0 kg |
| Weighted Dips | 20 kg | 1.0 kg |

> For **Weighted Pull-ups** and **Weighted Dips**, enter the *added load* only (e.g. if you do pull-ups with a 20 kg plate, enter 20). Toes to Bar is bodyweight only and has no 1RM field.

### How to set your 1RM

1. Tap the **SETTINGS** tab.
2. In the **BASELINE 1RM (KG)** card, tap the input field for each exercise.
3. Enter your current true 1RM (or a recent tested maximum). Use a conservative estimate rather than an optimistic one — the programme will push load progressively.
4. Your values are saved automatically as you type.

> 📌 **Best practice:** Test or conservatively estimate your 1RM before starting. A common estimation method is to take a recent heavy set and apply Epley's formula: `1RM ≈ weight × (1 + reps / 30)`.

---

## 3. Understanding the Programme Structure

The app runs a **12-week block periodization cycle** divided into three 4-week mesocycles. Each mesocycle has a distinct training focus and ends with a scheduled **deload week**.

```
WEEKS 1–4   → Phase 1: ACCUMULATION   (70–80% 1RM · RPE 7)
WEEKS 5–8   → Phase 2: INTENSIFICATION (80–90% 1RM · RPE 8)
WEEKS 9–12  → Phase 3: PEAKING         (87–97% 1RM · RPE 9)
```

### Deload weeks

Weeks **4, 8, and 12** are automatic deload weeks. The app uses the same weight prescriptions as the surrounding weeks but reduces set volume by ~40%. These are non-negotiable recovery weeks — do not skip them or add volume.

### Session types

Each week contains three session templates:

| Session | Exercises | Focus |
|---|---|---|
| **Session A** | Power Clean · Back Squat · Military Press · Weighted Pull-ups · Toes to Bar | Squat + Olympic + Press |
| **Session B** | Deadlift · Bench Press · Weighted Dips · Toes to Bar | Deadlift + Horizontal Push |
| **Plan B** | Power Clean · Back Squat · Bench Press · Weighted Pull-ups · Toes to Bar | Full body — single session |

> **Plan B** is provided for weeks where you can only train once. It combines elements of both sessions at moderate intensity.

### Toes to Bar rep scheme

Toes to Bar follows an independent rep progression across the 12 weeks, separate from the 1RM-based logic used for barbell lifts. Reps increase week by week and reset on deload weeks.

---

## 4. Navigating the App Tabs

The app has five tabs visible in the sticky navigation bar at the top. The active tab is highlighted in the current phase colour (blue → orange → purple as phases progress).

### SCHEDULE

The default home view. Shows the current week and phase at a glance.

- Use the **‹ ›** arrows to move between weeks 1–12. Navigating forward does not advance your active week — it is a preview tool.
- Each session card (A / B / Plan B) shows a preview of all prescribed weights for that session.
- Tap **START SESSION** on any card to open the live logging interface for that session.
- A deload banner appears automatically on weeks 4, 8, and 12.

### HISTORY

A chronological log of every completed and draft session.

- Completed sessions are marked with a green ✓ badge.
- Draft sessions (saved but not completed) are shown in amber.
- Tap the **✏️ edit** button on any session to re-open it in the logger and make corrections.
- Tap the **🗑 delete** button to permanently remove a session log (requires confirmation).

### PROGRESS

Visual performance charts for every barbell exercise.

- Each exercise has a canvas-based chart plotting logged working weights over the 12 weeks.
- A dashed **red baseline** line marks your original 1RM — any point above this line means you have exceeded your starting maximum in training.
- The **PRs card** at the top shows your all-time best logged weight for each exercise, along with the percentage gain over your baseline 1RM.

### SOURCE

Scientific references and methodology explanations. No interaction required.

- Explains the **block periodization** model and the peer-reviewed research backing the programme design.
- Details the **phase intensity bands**, **DUP (Daily Undulating Periodization)** logic used in Phases 2 and 3, and the **Toes to Bar** progression rationale.
- Useful for understanding *why* the programme is structured the way it is.

### SETTINGS

The control centre for the app. Contains three functional sections:

| Section | Function |
|---|---|
| **Cycle indicator** | Shows current cycle number and active week |
| **Baseline 1RM** | Edit your 1RM values for all 7 exercises |
| **Start New Cycle** | Export data, then reset and begin Cycle 2+ |
| **Export / Import** | Download or restore a full JSON data backup |

---

## 5. Logging a Session

1. From the **SCHEDULE** tab, tap **START SESSION** on Session A, B, or Plan B.
2. The logger opens with all sets and weights pre-populated based on your 1RM and session history.
3. For each exercise you will see a table of sets with three fields per row:

   | Field | What to enter |
   |---|---|
   | **Weight (kg)** | The actual weight you used (pre-filled with the recommendation) |
   | **Reps** | The reps completed for that set |
   | **RPE** | Your Rate of Perceived Exertion for that set (see section 9) |

4. Tick the **checkbox** on the left of each row when the set is done. The row turns green.
5. Use the **START TIMER** button after each set to run the recommended rest period (see section 8).
6. Expand the **WARM-UP** and **COOL-DOWN** sections at the top and bottom of the logger for session-specific protocols.
7. Add any free-text notes in the **Session Notes** field at the bottom.
8. When all sets are done, tap **COMPLETE SESSION** to save and mark the session as finished. The app will check for PRs automatically.

> 💾 **Save Draft:** Tap **SAVE DRAFT** at any time to save progress without marking the session complete. This lets you pause mid-session and resume later. Draft sessions appear in the HISTORY tab but do not count as completed for weight progression purposes.

---

## 6. The CrossFit Yesterday Toggle

If you trained CrossFit the day before a strength session, toggle on **"CrossFit yesterday?"** at the top of the logger before starting.

When active, the app automatically applies the following adjustments across all exercises in that session:

- **Working weights** reduced by **5%**
- **RPE target** reduced by **1 point**
- **Toes to Bar reps** reduced by approximately **15%**

The toggle also shows a visual amber highlight on the session header as a reminder that adjusted values are in use. This adjustment applies only to the current session and is not carried forward.

---

## 7. Understanding Weight Calculation Logic

The app uses a multi-stage algorithm to determine the recommended weight for each set.

### Week 1 and deload weeks

For the very first week of a cycle and all deload weeks (4, 8, 12), weights are calculated directly from your **baseline 1RM** multiplied by the phase percentage:

```
Recommended weight = round(1RM × phase_percentage, increment)
```

This provides a clean, conservative start and ensures recovery during deloads.

### All other weeks — adaptive progression

From Week 2 onwards, the app looks back through your completed session logs and applies the following logic:

1. **Find your most recent logged weight** for that exercise from any completed session.
2. **Check your average RPE** across the sets of that session.
3. **Determine your progression state:**
   - If RPE was **below 8** and all reps were completed → weight increases by one increment.
   - If RPE was **at 8–8.5** and all reps completed → weight is held.
   - If RPE was **above 8.5** or reps were missed → weight decreases by one increment.
4. **Detect stalls:** If the same top weight appears across three or more recent sessions without progression, the app considers the load stalled and recommends an increase.
5. **Apply a phase ceiling:** The calculated weight is always capped at the maximum percentage allowed for the current phase (e.g. 88% 1RM in Accumulation, 95% in Peaking) to prevent premature overreaching.

This means the app learns from your logged data over time. The more consistently you log, the more accurately it prescribes. **Entering RPE values is therefore not optional — it is core to how the algorithm works.**

---

## 8. The Rest Timer

Each exercise has a pre-set recommended rest period based on its neuromuscular demand:

| Exercise | Rest |
|---|---|
| Power Clean | 3:00 |
| Back Squat | 3:00 |
| Deadlift | 3:30 |
| Military Press | 2:30 |
| Bench Press | 2:30 |
| Weighted Pull-ups | 2:00 |
| Weighted Dips | 2:00 |
| Toes to Bar | 1:30 |

Tap the **clock icon** or **START TIMER** button after completing a set. The timer displays in large digits at the top of the logger view. An audible beep sounds when rest is complete. The timer uses the Web Audio API — you may need to tap the screen once to unlock audio on iOS.

---

## 9. RPE — Rate of Perceived Exertion

RPE is logged per set and is used by the weight progression algorithm. The app uses a 1–10 scale:

| RPE | Meaning |
|---|---|
| 6 | Light — could do 4+ more reps |
| 7 | Moderate — could do 3 more reps |
| 7.5 | Moderate-hard — could do 2–3 more |
| 8 | Hard — could do 2 more reps |
| 8.5 | Very hard — could do 1–2 more |
| 9 | Near max — could do 1 more rep |
| 9.5 | Max effort — maybe 1 more |
| 10 | True max — nothing left |

The target RPE rises with each phase: **7 in Accumulation, 8 in Intensification, 9 in Peaking**. Tap the **RPE LEGEND** button inside the logger at any time to view this reference table in-app.

---

## 10. Personal Records (PRs)

The app tracks your best logged weight for each exercise automatically. A PR is recorded whenever you log a weight that exceeds all previous entries for that exercise across every session and cycle.

- A **"NEW PR"** toast notification appears instantly when a PR is set during session completion.
- All PRs are visible in the **PROGRESS** tab alongside your baseline 1RM and the percentage gained.
- PRs are **preserved across cycles** — they are not cleared when you start a new cycle.

---

## 11. Deload Weeks

Weeks 4, 8, and 12 are automatic deload weeks. The app recognises them and:

- Displays a **⚡ DELOAD WEEK** banner in the SCHEDULE tab.
- Falls back to clean **1RM × phase percentage** weight calculations (no adaptive progression).
- Reduces sets by approximately 40% while maintaining the prescribed weights.
- Shows "DELOAD" in place of the intensity band in all headers.

Do not attempt to add sets or skip the deload — the programme's effectiveness depends on these recovery windows. Week 12 also serves as a **pre-test deload**: after completing it, test your new 1RMs before starting Cycle 2.

---

## 12. Exporting and Importing Data

Because all data lives in `localStorage`, it is critical to back up regularly. A single browser data clear will permanently erase everything.

### Export

1. Go to **SETTINGS**.
2. Tap **EXPORT JSON**.
3. A file named `scf_c[cycle]_[date].json` will be downloaded automatically.
4. Save it to iCloud, Google Drive, or any safe location.

The export file contains: cycle number, current week, all baseline 1RMs, every session log with sets/reps/RPE/notes, and all PRs.

### Import

1. Go to **SETTINGS**.
2. Tap **IMPORT JSON** and select a previously exported file.
3. All data (logs, 1RMs, PRs, cycle number, week) will be restored immediately.

> ⚠️ Importing overwrites all current data in the app. Always export first if you want to preserve what is currently saved.

---

## 13. Starting Cycle 2 — Restarting the Programme

After completing Week 12 and testing your new 1RMs, you are ready to begin a new cycle with updated baselines.

### Step-by-step

1. **Test your 1RMs** — After the Week 12 deload, perform max-effort testing for each lift. Use the PROGRESS charts to inform how much you expect to have improved.

2. **Update your baseline 1RMs** — Go to **SETTINGS → BASELINE 1RM** and enter your new tested values. Do this *before* clicking Start New Cycle.

3. **Export your Cycle 1 data** — Go to **SETTINGS** and tap **EXPORT JSON**. Store the file safely — this is your permanent record of Cycle 1.

4. **Start the new cycle** — In **SETTINGS**, tap the **START CYCLE 2 →** button. A confirmation prompt will appear:
   > ⚠️ This clears all session logs permanently.

   Tap **CONFIRM RESET** to proceed.

5. **What gets reset:**
   - All session logs → cleared
   - All PRs → cleared
   - Current week → reset to Week 1
   - Cycle counter → incremented to 2

6. **What is preserved:**
   - Your updated baseline 1RMs
   - App settings

The app header will now display **CYCLE 2** and the weight prescriptions will recalculate from your new baselines. The full 12-week structure restarts from Week 1 · Accumulation.

---

> **Data storage notice:** This app stores all data in the browser's `localStorage`. There is no cloud sync or account system. Treat your exported JSON files as your only backup. It is recommended to export after every completed session.
