# BTB Final Assessment Quiz
**BTB Data Analysis Bootcamp 2026 — Cohort 1**

A self-contained, browser-based multiple choice quiz for the final assessment of the BTB Data Analysis Bootcamp. No installation, no backend, no login required — just open the HTML file in any browser.

---

## What It Does

- 60 multiple choice questions across 5 modules
- 30-minute countdown timer that auto-submits when time runs out
- One question at a time with immediate feedback after each answer
- Pass mark of 31/60 (51%)
- Personalised result screen with score, grade and pass/fail banner
- Fully self-contained — works offline once downloaded

---

## Modules Covered

| Module | Questions |
|---|---|
| Excel | 15 |
| SQL | 15 |
| Power BI | 15 |
| General Data Analytics | 12 |
| Python | 3 |
| **Total** | **60** |

---

## Grading

| Grade | Score |
|---|---|
| Distinction | 80% and above (48–60) |
| Merit | 65–79% (39–47) |
| Pass | 52–64% (31–38) |
| Did not pass | Below 51% (0–30) |

Pass mark: **31 out of 60**

---

## How to Use

### Option 1 — Open locally
Download `BTB_Final_Assessment.html` and open it in any modern browser (Chrome, Firefox, Edge, Safari). No internet connection needed once downloaded.

### Option 2 — Host on GitHub Pages (recommended for sharing)
1. Create a free account at [github.com](https://github.com)
2. Create a new **public** repository named `btb-quiz`
3. Upload `BTB_Final_Assessment.html` to the repository
4. Go to **Settings → Pages → Source → main branch → Save**
5. Your shareable link will be:
   ```
   https://yourusername.github.io/btb-quiz/BTB_Final_Assessment.html
   ```
6. Share this link with students via WhatsApp or email — it opens directly in their browser

---

## How to Swap in New Questions

All 60 questions live in the `Q` array inside the `<script>` tag at the bottom of the HTML file. Each question follows this structure:

```js
{
  s: "Section name",        // Excel | SQL | Power BI | Analytics | Python
  q: "The question text",
  o: ["Option A", "Option B", "Option C", "Option D"],
  a: 1                      // Index of correct answer (0 = A, 1 = B, 2 = C, 3 = D)
}
```

To replace a question, find it in the array, update the `q`, `o` and `a` fields, and save the file. The quiz will reflect the changes immediately on next load.

---

## How to Change the Timer

Find this line near the top of the `<script>` block:

```js
let cur=0,score=0,answered=false,interval=null,left=1800,timedOut=false,name="";
```

Change `left=1800` to your desired duration in seconds:
- 30 minutes = `1800`
- 45 minutes = `2700`
- 60 minutes = `3600`

Also update the display text in the start screen and the timer default text to match.

---

## How to Change the Pass Mark

Find this line:

```js
const PASS=31;
```

Change `31` to any number between 1 and 60.

---

## Technical Notes

- Pure HTML, CSS and JavaScript — no frameworks, no dependencies, no CDN calls
- Works on mobile and desktop browsers
- Results are shown on screen only — no data is stored or transmitted anywhere
- Students should screenshot or note their score — there is no backend logging
- One attempt per session — refreshing the page resets the quiz

---

## Files

```
btb-quiz/
├── BTB_Final_Assessment.html    # The complete quiz — open this in a browser
└── README.md                    # This file
```

---

## Built For

**BTB (Beyond The Board) Data Analysis Bootcamp 2026**
Facilitator: Praise Njab
Cohort 1 — April to May 2026
