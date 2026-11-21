# 🎓 Student Attendance Tracker

A beautiful, fully offline **Faculty Attendance Management System** built with pure HTML, CSS, and JavaScript — no frameworks, no dependencies, no server required.

![HTML Only](https://img.shields.io/badge/Built%20With-HTML%20Only-orange?style=for-the-badge&logo=html5)
![No Dependencies](https://img.shields.io/badge/Dependencies-None-brightgreen?style=for-the-badge)
![Offline](https://img.shields.io/badge/Works-Offline-blue?style=for-the-badge)
![localStorage](https://img.shields.io/badge/Storage-localStorage-purple?style=for-the-badge)
![CSS Magic](https://img.shields.io/badge/CSS%20Magic-10%20Tricks-violet?style=for-the-badge)

---

## 🔄 Latest UI Update (November 2026)

- Redesigned the **Statistics** tab with a cleaner dashboard layout, improved weekly attendance bars, and more readable low-attendance table.
- Removed accidental extra HTML comment closers that were appearing as visible `-->` arrows across the page.
- No attendance logic, data, or other functionality was changed.

---

## ✨ Features

### Core Functionality
- 🏫 **Division & Batch Selector** — Filter students by Division (A/B/C/D) and Batch (1/2/3)
- ✅ **Take Attendance** — Present/Absent toggle per student; **stats update live instantly on every click** (no Submit needed to see counts)
- 🔢 **Live Stats Bar** — Total / Present / Absent / Rate counters update in real time as you mark students
- ❌ **Live Absent Summary** — Absent student name chips appear/disappear immediately on toggle
- 🔍 **Search Bar** — Instantly filter students by name or roll number
- 📊 **Weekly Attendance Chart** — Visual bar chart showing attendance % for Mon–Sat
- ⚠️ **Low Attendance Alert** — Statistics tab shows **only students below 75%** attendance, sorted worst-first with 🔴🟠 warning icons
- 🔄 **Reset Button** — Resets all attendance counts to zero (with confirmation)
- ➕ **Add Student** — CSS-only `:target` modal (no JS!) to add a new student
- ➖ **Remove Student** — Remove any student per row with a single click
- 💾 **Persistent Storage** — All data saved in browser `localStorage` (survives refresh)
- 🔔 **Toast Notifications** — Instant animated feedback for every action

### Visual & UI Features (CSS-Only Magic)
1. 🌗 **Dark/Light Mode Toggle** — Pure CSS checkbox hack, no JS
2. 🎭 **Animated Gradient Background** — 12-second infinite gradient animation
3. ✨ **Glowing Neon Card Borders** — Purple glow + lift on hover
4. 🃏 **Expandable Student Rows** — `<details><summary>` with weekly breakdown
5. 🗂️ **CSS-Only Tab Switching** — 3 tabs with radio-button CSS selectors
6. 🔍 **CSS Tooltips** — `::after` pseudo-element, no JS, no libraries
7. 🎯 **Animated Progress Bars** — Fill animation with CSS custom property `--pct`
8. 🏷️ **Ribbon Badges** — `::before` clip-path ribbon on section cards
9. 🌈 **Zebra Gradient Table Rows** — nth-child gradient alternating rows
10. 💫 **Shimmer Skeleton Loader** — 1.5s shimmer effect on card load

---

## 🚀 Getting Started

### Option 1 — Just open it
```
Double-click index.html
```
That's it. No install, no build step, no internet needed.

### Option 2 — Clone from GitHub
```bash
git clone https://github.com/YOUR_USERNAME/student-attendance-tracker.git
cd student-attendance-tracker
# Open index.html in your browser
```

---

## 📁 Project Structure

```
student-attendance-tracker/
│
├── index.html          # Entire app — HTML + CSS + JS in one self-contained file
├── README.md           # This file
└── AttendanceTracker.zip  # Portable archive of both files
```

---

## 🖥️ How to Use

1. **Select Division & Batch** from the dropdowns to filter your class
2. **Pick a date** using the date picker (defaults to today)
3. **Mark attendance** — click **P** (Present) or **A** (Absent) for each student
4. Click **Submit Attendance** to save to localStorage
5. Click any student row to **expand** and see their weekly breakdown
6. Switch to the **📊 Statistics** tab to see the weekly attendance chart and low-attendance students
7. Switch to the **👥 Students** tab for a card-grid overview of all students
8. Check the **Absent Summary** section for absent student name chips
9. Click **Reset** to clear all attendance data (a confirmation will appear)
10. Toggle **☀️/🌙** in the top-right to switch between light and dark mode

### Managing Students
- Click **➕ Add Student** → modal opens (pure CSS `:target`) → fill details → Save
- Expand a student row → click **🗑 Remove** to delete that student

---

## 💫 CSS Magic (No JavaScript)

All 10 visual features below work **entirely in CSS** — zero JS involved for visuals.

| # | Feature | CSS Technique |
|---|---------|---------------|
| 1 | 🌗 Dark/Light Mode Toggle | `<input type="checkbox">` + `:checked ~ .app-wrapper` sibling selector rewrites all CSS variables |
| 2 | 🎭 Animated Gradient Background | `background-size: 400% 400%` + `@keyframes gradientShift` animating `background-position` over 12s |
| 3 | ✨ Glowing Neon Card Borders | `card:hover { box-shadow: 0 0 15px #7c3aed, ... }` + `transform: translateY(-4px)` |
| 4 | 🃏 Expandable Student Rows | Native `<details><summary>` HTML elements, styled with `details[open]` + CSS transitions |
| 5 | 🗂️ CSS-Only Tab Switching | `<input type="radio">` + `:checked ~ .tab-panels #panel-X { display: block }` |
| 6 | 🔍 CSS Tooltips | `[data-tooltip]::after { content: attr(data-tooltip); opacity: 0 }` + `:hover::after { opacity: 1 }` |
| 7 | 🎯 Animated Progress Bars | `@keyframes fillBar { from {width:0%} to {width:var(--pct)} }` using inline CSS custom property |
| 8 | 🏷️ Ribbon Badges | `.card::before { clip-path: polygon(...); position: absolute; top-right }` |
| 9 | 🌈 Zebra Gradient Rows | `tr:nth-child(even) { background: linear-gradient(...) }` + `:hover` variant |
| 10 | 💫 Shimmer Skeleton Loader | `@keyframes shimmer { background-position: -200%→200% }` on `card::after`, fades out after 1.5s |

---

## 📊 Statistics Tab\n\nThe Statistics tab contains the weekly attendance chart and the low-attendance student list. The Overall Summary card has been removed.\n\n---\n\n## 🏆 What Makes It Unique

> This isn't just another attendance tracker — it's a **CSS engineering showcase**.

- **Zero JS for UI**: Every visual interaction — theme switching, tabs, tooltips, modals, progress bars, hover effects — is powered entirely by CSS.
- **`:target` Modal**: The Add Student modal opens/closes using only `<a href="#add-modal">` and CSS `:target` — no `addEventListener`, no `classList.toggle`.
- **CSS Variable Animations**: Progress bars use `--pct` custom properties set inline by JS (data) but animated purely by CSS `@keyframes`.
- **Sibling Selector Theme Engine**: The dark mode toggle works by checking a `<input type="checkbox">` and using `~` sibling combinator to cascade variable overrides to the entire app wrapper.
- **Self-Contained**: The entire app — 1200+ lines — is one `.html` file you can email, share on a USB drive, or host anywhere with zero build tooling.

---

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| HTML5 | Structure, `<details>`, `<summary>`, `:target` modal |
| CSS3 | All visual features, animations, theme, tabs, tooltips |
| Vanilla JavaScript | Attendance logic, localStorage, DOM rendering |
| localStorage API | Data persistence across sessions |

> ⚡ Zero external libraries. Zero npm. Zero build tools. Zero network requests.

---

## 📸 Sample Data

Comes pre-loaded with **20 students** across two divisions and two batches:

| Division | Batch | Students |
|---|---|---|
| A | 1 | Aarav Shah (101), Priya Patel (102), Rohan Mehta (103), Sneha Joshi (104), Yash Kumar (105) |
| A | 2 | Ananya Singh (106), Karan Verma (107), Meera Nair (108), Dev Sharma (109), Riya Gupta (110) |
| B | 1 | Arjun Reddy (111), Kavya Iyer (112), Nikhil Das (113), Pooja Desai (114), Siddharth Rao (115) |
| B | 2 | Tanvi Bhatt (116), Vikram Jain (117), Zara Khan (118), Aditya Nair (119), Bhavna Shah (120) |

---

## 📄 License

This project is open-source and free to use under the [MIT License](https://opensource.org/licenses/MIT).

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you'd like to change.

---

> Made with ❤️ for faculty who want a simple, fast, beautiful way to track attendance — with a little CSS wizardry on the side. 🧙‍♂️
