# High-quality work to drive traffic to Mallo landing page

Actionable ideas to grow **qualified traffic** (people who match the ICP: living alone, new city, remote work, want a daily companion that remembers them). Focus on value-first, then conversion to the app.

---

## 1. Content & SEO (highest leverage, compounds over time)

### New articles that match search intent
- **"Best AI companion apps that remember you (2025)"** – Honest comparison including Mallo; target "AI companion app", "app that remembers you". Be useful, not salesy.
- **"Why I feel lonely working from home"** – Long-tail; link to wellbeing check + app.
- **"First month in a new city: what actually helps"** – Extend the 7-day guide; internal link to `/tools/guide.html` and articles.
- **"Daily check-in questions that actually help"** – Target "daily reflection questions", "one question a day"; link to `/tools/daily.html` and app.
- **"Is an AI companion right for me?"** – Answer post; link to quiz and app. Aim for featured snippet.
- **Seasonal** – Expand holiday loneliness (Thanksgiving, NYE alone, Valentine's when single); update each year.

### On-page SEO improvements
- Add an **Articles / Resources index** (`/articles/index.html`) that lists all articles and tools with short descriptions. Improves internal linking and crawlability.
- Ensure every article has **2–3 internal links** to another article, a tool, or the app CTA.
- Add **FAQ schema** or **HowTo** where it fits (e.g. guide page already has HowTo).
- Target **"People also ask"** in key articles: add a short FAQ block with question-style H2s and clear answers.

### Keyword alignment
- Use one primary keyword in: `<title>`, first H1, first 100 words, one subheading.
- Tools already target: "AI companion quiz", "first week new city", "daily check-in question", "remote work wellbeing". Double-check meta titles/descriptions match what people type.

---

## 2. Tools that attract and convert

### Make tools more shareable
- **Quiz & Wellbeing result pages**: Dynamic **OG image** per result (e.g. "You'd benefit from something that checks in on you" + Mallo logo). When shared on X/LinkedIn, the card shows the result + CTA. Requires server-side or a small image service.
- **"Share my result"** – Already have Copy link + Share on X; add "Share to LinkedIn" or "Download image" (result as image) for higher share rate.
- **Daily question**: "Share today's question" with pre-filled tweet: question text + link to daily.html. Different question each day = repeat visits and shares.

### New tools (if capacity allows)
- **"Am I lonely?" short check** – 3–5 questions, gentle result + suggestions; links to wellbeing check and app. Target "am I lonely quiz".
- **"Relocation readiness checklist"** – Printable or on-page checklist (documents, first week tasks); link to 7-day guide and app for "after you move".
- **"One sentence journal prompt"** – One prompt per day (like daily question); link to app for "every day + memory".

### Tool → App path
- Every tool ends with the same CTA (you have this). Optionally: **"Get this in the app"** line under each tool (e.g. "In Mallo you get one question every day and it remembers your answers").

---

## 3. Distribution & partnerships (quality over quantity)

### Where your ICP already is
- **Reddit** – r/remotework, r/WorkFromHome, r/expats, r/IWantOut, r/lonely (rules vary; participate genuinely, share tools when relevant, no link spam).
- **Indie / remote-work newsletters** – Pitch a short feature or guest tip ("one tool that helped me when I moved cities"); link to guide or quiz.
- **Product Hunt / BetaList** – Launch or "tools for remote workers" lists; link to landing page and one hero tool (e.g. quiz).
- **App directories** – "Apps for people who live alone", "Mental wellness apps", "Apps for remote workers"; ensure listing URL is mallopal.com or a deep link to a tool.

### Collaborations
- **Bloggers / creators** in relocation, remote work, or "living alone" – Offer a free tool (e.g. embed "today's question" or link to 7-day guide) in exchange for a mention or backlink.
- **Therapists / coaches** (with clear boundaries: not therapy) – "Resource for clients who want a low-pressure daily check-in" – link to tools and app disclaimer.

---

## 4. Social & repeat visits

### Low-effort, high-signal
- **"Today's one question"** – Post the daily question on X/Instagram/LinkedIn with link to `/tools/daily.html`. Same URL, new question each day = reason to click again.
- **Quiz result quotes** – Turn result headlines or tips into short posts (e.g. "You don't need another productivity tool. You might need one low-pressure thread.") with link to quiz or app.
- **7-day guide** – One day per day for a week (Day 1 tip, Day 2 tip…) with link to full guide.

### User stories (with permission)
- Short quotes or 1–2 sentence stories from real users (moved city, WFH, living alone) on the landing page or a dedicated "Stories" section. Builds trust and gives shareable content.

---

## 5. Technical & conversion

### Landing page split testing (A/B) for best iOS traffic

**When it’s worth it:** Once you have steady traffic (organic or paid), high-quality split tests are one of the best ways to improve conversion to App Store clicks and installs. Don’t split-test everything at once—run one clear test at a time.

**What to test (high impact):**
- **Hero headline + lead** – e.g. benefit-focused vs “remembers you” vs “checks in so you’re not alone.” Use a custom dimension in GA4 so you can segment conversions by variant.
- **Primary CTA copy** – “Get Mallo on iPhone” vs “Try Mallo free” vs “Download free.” Track `click_to_app_store` by variant.
- **Entry point** – Send paid/organic traffic to landing vs quiz vs guide and compare install rate (UTMs + GA4 already support this; formalize as an experiment).
- **Sticky CTA** – Test showing a small “Get Mallo” bar on scroll vs no sticky (see “Conversion on the page” below).

**Quality bar:**
- **One test at a time** so you know what moved the needle.
- **Primary metric:** App Store link clicks (you already track this); ideally also installs via App Store Connect / attribution.
- **Run to significance** – use a calculator or GA4’s experiment duration guidance; don’t stop early.
- **SEO care:** If you test the H1 or meta, prefer server-side or edge-based tests so crawlers see one canonical version; otherwise test only below-the-fold or CTA copy.

**Implementation options:**
- **GA4 + cookie-based variant:** Small script assigns a variant on first visit (e.g. 50/50), sets a cookie, and sends `gtag('set', 'user_properties', { experiment_variant: 'A' | 'B' })`. Swap hero/CTA in JS. Simple but can cause a brief flash; acceptable for CTA-only tests.
- **Google Optimize (deprecated)** – not recommended for new setup.
- **Server-side or edge (e.g. Vercel Edge, Cloudflare Workers):** Assign variant by hashed user ID or random, serve the right HTML. No flash, SEO-safe. Best for headline tests.
- **Third-party:** Optimizely, VWO, or similar if you want a UI and built-in stats.

Start with one CTA or one hero copy test; use your existing `click_to_app_store` event and a `user_properties` (or event param) for the variant so you can compare conversion rate by variant in GA4.

---

### Site health
- **Core Web Vitals** – Keep LCP, FID, CLS good (you have preload for hero image; watch for heavy scripts).
- **Mobile-first** – Tools and articles already responsive; test on real devices.
- **Sitemap** – You have one; submit in Search Console and add new URLs when you publish.

### Conversion on the page
- **Sticky CTA** – Optional: small "Get Mallo" bar or button visible on scroll (especially on tool result pages).
- **Exit intent** – Optional: lightbox or banner on tool completion ("Before you go – get the full experience in the app") with one tap to App Store.
- **UTM consistency** – You use `utm_source=quiz|guide|daily|wellbeing`; add `utm_source=article` for article CTAs so you can see which content drives installs.

---

## 6. Paid (targeted, measurable)

### Apple Search Ads
- Keywords: "AI companion", "companion app", "app that remembers you", "daily check-in app", "loneliness app", "living alone app". Bid on your brand.
- Send traffic to landing page (not direct to App Store) for quiz or hero; capture intent then convert.

### Meta / Google
- Audiences: interests like "remote work", "relocation", "living alone"; lookalikes from site visitors or quiz completers.
- Creative: result-style cards ("Is an AI companion right for you? Take the quiz") or "Your first 7 days in a new city – free guide".
- Retargeting: visitors who did quiz or wellbeing but didn’t click App Store.

---

## Priority order (suggested)

1. **Articles index + 2–3 new SEO articles** (content compounds; internal linking helps all pages).
2. **Shareability of tools** (OG per result, "Share today's question" pre-filled tweet).
3. **One new tool or checklist** if you have copy (e.g. relocation checklist or "am I lonely" short check).
4. **Daily/social habit** (post today's question or one guide day with link).
5. **Partnerships** (one newsletter or one Reddit/community where you add value and link when natural).
6. **Paid** once you have conversion data (which tool or article converts best).

---

*This doc lives in `landingpage/docs/` for the team. Update as you ship and learn.*
