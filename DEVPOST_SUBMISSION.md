# Devpost submission — AccessPilot AI

**Tagline:** Make digital experiences more inclusive with privacy-first accessibility intelligence.

**Hackathon:** SLAY HACKS 2026

**Participant:** Samer Tallauze (solo; current student enrollment self-attested)

## Inspiration

Digital experiences still create avoidable barriers. Many teams know accessibility matters but struggle to translate implementation details into actionable, prioritized fixes. We built AccessPilot AI to make the first audit accessible to designers, developers, and student builders.

## What it does

AccessPilot AI analyzes pasted HTML locally in the browser and surfaces accessibility concerns in a clear, prioritized interface. It examines document language, page titles, main landmarks, image alternatives, labels, buttons, link purpose, heading structure, iframes, and ARIA-button patterns. It explains why each rule fired and shows a practical example of a possible fix. Users can switch between realistic sample pages and export findings as JSON or HTML.

## How we built it

A dependency-free frontend uses semantic HTML, responsive CSS, JavaScript and the browser DOMParser. Deterministic accessibility checks identify evidence. A transparent three-nearest-neighbors classifier, trained on twelve disclosed synthetic examples, ranks findings as high, medium, or low priority based on estimated impact, prevalence, and persistence. No user content leaves the browser; no API key or account is needed.

## Challenges

A key product decision was keeping findings evidence-based and treating ML ranking as a suggestion rather than a compliance verdict. We also kept the interface keyboard-operable, exportable, and entirely local.

## Accomplishments

A runnable client-side prototype with sample scenarios, 10 audit-rule categories, explainable ranking, responsive UI, and portable report exports. The model and evaluation limitations are documented rather than hidden.

## What we learned

Automated checks catch only a subset of accessibility concerns. Humans must verify keyboard behavior, assistive technology, contrast, interaction state, and inclusive usability. Privacy and explainability are essential for responsible AI tooling.

## What's next

Broaden the ruleset, incorporate axe-core for richer programmatic checks, test with accessibility practitioners, add optional rendered-page analysis, and validate the ranking on annotated real-world examples before treating the classifier as predictive.

## Built with

HTML5, CSS3, JavaScript, DOMParser, k-nearest neighbors, WCAG-informed heuristics.

## Submission links

**Live demo:** https://accesspilot-ai-samertalls-projects.vercel.app (Vercel production deployment READY; independently checking public access remains recommended).

**Public source:** https://github.com/samertall/accesspilot-ai

**Video:** https://accesspilot-ai-samertalls-projects.vercel.app/accesspilot-demo.mp4 — 3:07 narrated walkthrough assembled from genuine browser captures; for an embedded Devpost video field, upload this MP4 to YouTube or Vimeo and provide that URL.

**Screenshots:** [Checkout](https://accesspilot-ai-samertalls-projects.vercel.app/screenshots/01-checkout.jpg), [Article](https://accesspilot-ai-samertalls-projects.vercel.app/screenshots/02-article.jpg), [Accessible page](https://accesspilot-ai-samertalls-projects.vercel.app/screenshots/03-accessible.jpg) — captured from the working application in Chromium.

**Reviewer note:** This is an educational, browser-only accessibility assistant; not an accessibility certification or a production-validated predictive model.
## Development assistance disclosure

The project code, documentation and demonstration assets were produced with AI assistance at the participant's direction. The on-device 3-nearest-neighbors classifier was built using twelve explicitly synthetic examples. This illustrative ranking is neither real-world validated nor a calibrated predictor of impact.
