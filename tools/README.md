# Free tools – lead and traffic

All copy in this folder is **human-written** for Mallo’s ICP: people who live alone, relocated, work remotely, or have high-stress roles and want a daily companion that remembers them.

Use these tools to **help users** (real value, no fluff) and **drive maximum traffic** to the app (shareable results, no email gate, SEO-optimised pages, clear CTA to download Mallo).

## Live pages (SEO-optimised)

| Page | URL | Purpose |
|------|-----|--------|
| **Weekly recap** | `/tools/weekly.html` | “Free weekly recap” – copy a Mallo-style prompt, run it in ChatGPT/Claude, then download a shareable recap card |
| **Quiz** | `/tools/quiz.html` | “Is an AI companion right for you?” – 5 questions, 3 results, shareable `?result=strong_fit|good_fit|curious` |
| **Guide** | `/tools/guide.html` | “Your first 7 days in a new city” – full guide with HowTo schema, static content |
| **Daily** | `/tools/daily.html` | “Today’s one question” – one question per day (day-of-year % 15), rotates daily |
| **Wellbeing** | `/tools/wellbeing.html` | “Remote work & living alone wellbeing check” – 5 questions, 3 results, shareable `?result=high_need|moderate|doing_ok` |

Each page has: unique `<title>` and meta description, canonical URL, Open Graph and Twitter Card, JSON-LD (Quiz or HowTo/WebApplication), breadcrumbs, UTM on App Store links (`utm_source=quiz|guide|daily|wellbeing`), and share buttons (Copy link, Share on X) on result screens.

---

## 1. Quiz: Is an AI companion right for you?

**File:** `quiz-is-ai-companion-right-for-you.json`

- **What it is:** 5 questions → 3 result types (strong fit / good fit / curious). User gets honest, specific copy and a soft CTA to try Mallo.
- **Scoring:** Sum the `scoring[optionValue]` for each selected option. Map total to `results[].scoreRange` (e.g. 8–15 → strong_fit, 5–7 → good_fit, 0–4 → curious).
- **No signup.** Show result on same page; add “Share my result” (link or image) to drive viral traffic.
- **SEO:** Title/meta in `meta`. Use slug `quiz` for URL (e.g. `/tools/quiz/`).

---

## 2. First 7 days in a new city

**Files:** `guide-first-7-days-new-city.md` (canonical) and `guide-first-7-days-new-city.json` (for dynamic UIs).

- **What it is:** One small, concrete task per day (e.g. “One place that’s yours”, “One human exchange”). Ends with CTA to Mallo.
- **Use:** Render all 7 days on one page, or one day per page with prev/next. Link from “New city / relocated” content and forums.
- **SEO:** Target “first week new city”, “moving to new city checklist”, “relocation guide”. Slug: `guide-new-city`.

---

## 3. Today’s one question (daily check-in)

**File:** `daily-check-in-questions.json`

- **What it is:** 15 questions; show one per day (rotate by day-of-year or `(dayOfYear % 15)` so everyone sees the same question on the same calendar day).
- **Flow:** User sees question → optional short answer (not stored) → show `response` line → CTA to Mallo (“Want this every day and someone who remembers?”).
- **No signup.** Same URL daily; different question. Good for repeat visits and shares (“Today’s question was…”).
- **SEO:** “Daily check-in question”, “one question a day”. Slug: `daily-question`.

---

## 4. Remote work & living alone wellbeing check

**File:** `remote-wellbeing-check.json`

- **What it is:** 5 questions → 3 result types (high_need / moderate / doing_ok). Each result has headline, body, and 2–3 **actionable suggestions** (not generic advice).
- **Scoring:** Sum `scoring[optionValue]` for selected options. Map total to result by `scoreRanges` (8–10 → high_need, 4–7 → moderate, 0–3 → doing_ok).
- **No signup.** Result page ends with CTA to Mallo.
- **SEO:** “Remote work loneliness”, “working from home wellbeing”, “living alone check”. Slug: `wellbeing-check`.

---

## Implementation notes

- **No email gate.** All tools are usable and valuable without signup. CTA to the app is the only “conversion” on the page.
- **Shareability:** For quiz and wellbeing check, add “Share my result” (e.g. open graph with result headline + mallopal.com/tools/quiz). For daily question, “Share today’s question” with the question text.
- **Weekly recap:** Designed to create a shareable artifact (downloadable image card). The prompt is generated client-side; user runs it in their preferred AI, then pastes results back to make a card.
- **UTM:** Append `?utm_source=quiz` (or `guide`, `daily`, `wellbeing`) to App Store links so you can measure which tool drives installs.
- **Consistent CTA:** Every tool ends with the same idea: “Mallo checks in on you, remembers you, no pressure.” Button: “Try Mallo (free to start)” → App Store.

---

## File overview

| File | Purpose |
|------|--------|
| `quiz-is-ai-companion-right-for-you.json` | Quiz content, scoring, result copy, CTA |
| `guide-first-7-days-new-city.md` | Full 7-day guide (human-readable) |
| `guide-first-7-days-new-city.json` | Same guide for dynamic rendering |
| `daily-check-in-questions.json` | 15 questions + response lines + rotation note |
| `remote-wellbeing-check.json` | Wellbeing check questions, scoring, results, suggestions |
| `README.md` | This file |

All copy is written for clarity, empathy, and alignment with Mallo’s voice: warm, honest, no hype, no therapy claims.
