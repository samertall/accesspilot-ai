# AccessPilot AI

**Live demo:** https://accesspilot-ai-samertalls-projects.vercel.app  
**Source:** https://github.com/samertall/accesspilot-ai  
**Video:** https://accesspilot-ai-samertalls-projects.vercel.app/accesspilot-demo.mp4

An original, privacy-first, browser-based accessibility source auditor with explainable ML-assisted issue ranking, prepared for SLAY HACKS 2026.

## Quick start

Open `index.html` directly in a recent browser. No server, API keys, tracking, build step, or network connection is necessary. Optional: `python -m http.server 8000` and visit `http://localhost:8000`.

## Demonstration

1. Select **Checkout form** and click **Analyze accessibility**.
2. Explore prioritized issues and copy suggested fixes.
3. Switch to **News article** to exercise additional rules.
4. Select **Accessible page** to view a no-issues result within supported checks.
5. Export JSON or HTML report.

## Implementation

- The source HTML is parsed with the browser's DOMParser API, within the browser, and never uploaded.
- Ten WCAG-informed categories: document language, page title, main landmark, image alternative text, form labels, button names, link purposes, heading hierarchy, iframe titles, and custom ARIA-button keyboard concerns.
- Priority is proposed with a **3-nearest-neighbors classifier** using inverse-distance weighted voting over 12 handcrafted **synthetic training examples**. Inputs represent estimated impact (user blocking), prevalence, and persistence; each issue type has disclosed fixed characteristics. The classifier is illustrative, not empirically validated, and confidence is a neighborhood vote fraction, **not calibrated probability**.
- Classification affects only sort order and labels; deterministic rules establish findings.
- Exports are generated using browser Blob APIs.

## Limitations and safety

- **Not a WCAG compliance checker or accessibility certification.** Static markup checks cannot verify contrast, screen readers, keyboard flows, responsive layouts, runtime states, focus order, or lived usability.
- The source checker is conservative and will produce some false positives and miss some issues. Semantic accessibility depends on context. Inline sample data is fictional.
- No external AI API is used and no production-trained model is claimed.
- No cookies, telemetry, server, or outbound requests are needed.

## File structure

- `index.html` — semantic, responsive UI
- `styles.css` — responsive high-contrast design
- `app.js` — auditing rules, small ML ranking model, sample workflows, report exports
- `screenshots/01-checkout.jpg`, `screenshots/02-article.jpg`, `screenshots/03-accessible.jpg` — authentic Chromium screenshots from executed app flows
- `accesspilot-demo.mp4` — narrated, three-minute demo assembled from genuine Chromium screen captures of the working application
- `DEVPOST_SUBMISSION.md` — submission-ready text and the deployed public demo link

## Deployment

Deployed via GitHub-connected Vercel production: https://accesspilot-ai-samertalls-projects.vercel.app

Vercel reports deployment `dpl_AwGXu5ZeSCpfVWdbXtn3gqEdzrKm` as READY and authentication protection disabled. The deployment is sourced from this repository's `main` branch. Independent browser HTTP access could not be established in the current environment.

## Local validation

Executed in headless Chromium using the same HTML/CSS/JavaScript: checkout 6 findings, news article 11, accessible example 0; no JavaScript runtime errors. This validates the local application, not the public delivery path.

## Ownership and third-party assets

Original educational hackathon prototype. No external assets or packages.
## AI-assisted development disclosure

Implementation, testing assistance, and submission materials were prepared with AI assistance at the participant's direction. Issue identification uses deterministic rules; the small 3-nearest-neighbors ranking model uses twelve handcrafted synthetic examples and is not empirically validated as a predictive severity model.
