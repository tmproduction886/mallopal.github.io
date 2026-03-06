# MalloPal landing page (mallopal.com)

Landing page for the Mallo iOS app. Built for **SEO** and the **ICP** (Ideal Customer Profile): English-market, 25–40, living alone / relocated / remote; wants to be remembered, proactive check-ins, a relationship that gets deeper each week.

## Contents

- **index.html** – Single-page site with semantic HTML, JSON-LD (WebPage, WebSite, SoftwareApplication, FAQPage), Open Graph, and keyword-rich copy.
- **styles.css** – Mallo brand colors (cream, brown, accent), hero with app visual, responsive layout.
- **privacy/index.html** – Privacy Policy page. Canonical: https://mallopal.com/privacy/
- **terms/index.html** – Terms of Service page. Canonical: https://mallopal.com/terms/
- **manifest.json** – Web app manifest (name, icons, theme). Used for PWA / Add to Home Screen.
- **assets/**
  - **hero-app.png** – Original app launch visual source (2048×2048). Used to generate smaller social/preview assets.
  - **og-image.jpg** – 1200×630 social share image (OG/Twitter). Optimized for fast fetch by crawlers.
  - **app-icon.png** – App icon (1024×1024, from iOS AppIcon). Used as favicon.
  - **app-icon-192.png** – App icon 192×192. Used as Apple touch icon fallback.
  - **app-store-badge.svg** – Legacy local badge (kept for reference). The site now uses Apple’s official hosted badge via App Store Marketing Tools for pixel-perfect rendering on iOS.

## Where the app icon appears

- **Search results** (Google, Bing) – Favicon (`rel="icon"`) is the site icon next to the result.
- **Browser tab** – Favicon; **Add to Home Screen** (iOS) – Apple touch icon.
- **PWA / install** – `manifest.json` icons.
- **Structured data** – Organization `logo` and SoftwareApplication `image` in JSON-LD point to the app icon so search/knowledge panels can show it.

## Before deploy

1. **App Store link** – In `index.html`, replace `https://apps.apple.com/app/mallopal/idXXXXXXXXX` with your real App Store URL.
2. **OG image** – For best social previews, we use `assets/og-image.jpg` (1200×630) and set `og:image` / `twitter:image` to `https://mallopal.com/assets/og-image.jpg`.

## Domain

Canonical URL: **https://mallopal.com/**  
All meta and JSON-LD use this domain.

## SEO

- Title: “Mallo – AI Companion That Remembers You | MalloPal”
- Meta description and first paragraph include: AI companion, remembers you, daily check-in, weekly recap, living alone, relocated, remote.
- FAQ section targets long-tail queries (e.g. “Is Mallo good for people who live alone?”).
- Structured data: WebPage, WebSite, Organization, SoftwareApplication, BreadcrumbList, FAQPage.
