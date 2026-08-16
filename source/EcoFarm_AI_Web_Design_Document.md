# EcoFarm AI — Web Design Document v1.0

## 1. Design Objective
Create a premium, calm, nature-led AI product experience communicating three ideas immediately: **AI Vision, EcoMind, and Safety-first agricultural intelligence**.

The design should use strong hierarchy, generous whitespace, responsive layouts, reusable components, subtle motion, and clear conversion paths. Framer is the visual reference for responsive composition, components, CMS/content patterns, motion, and polished publishing — not for copying its branding or proprietary assets.

## 2. Brand Personality
**Intelligent · Natural · Trustworthy · Calm · Transparent · Practical · Premium · Responsible**

Avoid a futuristic robot aesthetic. EcoFarm AI should feel connected to crops, soil, climate, and real agricultural decisions.

## 3. Visual System
- Deep forest green, natural leaf green, warm off-white, charcoal, and earth neutrals.
- Fresh agricultural green for primary actions and positive states.
- Amber for verification/warning; restrained red for blocked/critical states.
- Modern sans-serif typography with strong display hierarchy.
- Soft rounded cards and controls.
- High-quality crop, farm, soil, weather, and environmental imagery.
- Simple consistent line icons.

## 4. Information Architecture
- Home
- How It Works
- AI Vision
- EcoMind
- Safety
- Demo
- Insights / Guides
- About

Primary CTA: **Analyze a Crop**.

## 5. Homepage
1. Header and primary CTA.
2. Hero: “AI crop intelligence that makes uncertainty actionable.”
3. DEMO MODE / Safety-first / Evidence-aware / Provenance-visible trust strip.
4. Product preview with crop image, analysis, confidence, weather provenance, and EcoMind.
5. Three feature cards: AI Vision / EcoMind / Safety-first.
6. Workflow: Upload → Add Context → Analyze → Review Confidence → Verify / Act.
7. Safety section demonstrating low-confidence blocking and moderate-confidence verification.
8. Impact section showing quantitative impact only when baseline data exists.
9. Differentiation section.
10. Final CTA and footer.

## 6. AI Analysis UI
- Upload zone with image preview.
- Analysis card with crop condition, evidence, confidence, and recommendation state.
- Confidence states: Low / Moderate / Permitted.
- Low confidence: blocked.
- Moderate confidence: manual verification required.
- Weather card with timestamp/source/provenance.
- EcoMind card with score and prototype/validation status.
- Impact card only when a valid baseline exists.

## 7. Safety UX
Safety must be part of the interface, not hidden in a disclaimer.

| State | UI behavior | Action |
|---|---|---|
| Low confidence | Blocked warning state | Do not recommend action |
| Moderate confidence | Verification state | Ask user to verify manually |
| Permitted | Evidence-backed result | Show recommendation with limitations |
| Missing baseline | Neutral explanation | Do not show invented impact |
| Demo mode | Persistent DEMO MODE indicator | Make synthetic nature obvious |

## 8. Responsive Design
**Desktop:** wide hero split, multi-column cards, 2–3 column analysis layouts.

**Tablet:** partially stacked hero, two-column feature sections, simplified analysis cards.

**Phone:** single-column flow, compact CTA, vertically stacked cards, safety status always visible.

## 9. Components
Button; Feature Card; Confidence Badge; Analysis Card; Weather Card; Provenance Row; Safety Banner; Navigation; Image Upload; CTA Section.

Each should have explicit variants such as Primary/Secondary, Low/Moderate/Permitted, Blocked/Verify/Informational, and Empty/Uploading/Preview/Error.

## 10. Motion
Use restrained crop scanning, progressive evidence reveal, confidence transitions, card elevation, and smooth section transitions. Avoid excessive parallax, particles, or animation that competes with safety messaging. Support reduced motion.

## 11. Accessibility & Performance
Use accessible contrast, keyboard navigation, visible focus, readable type, descriptive image alternatives, clear form labels, non-color-only safety states, and reduced-motion support. Optimize images, lazy-load below-the-fold media, limit third-party scripts, and keep animation purposeful.

## 12. Demo Mode
When enabled, make `DEMO MODE` obvious and disclose that results are synthetic, not live model predictions. Demo flow: Open → Upload → Add Context → Analyze → Evidence → Confidence → Weather Provenance → EcoMind → Safety Panel → Baseline-dependent Impact.

## 13. Suggested Copy
- Hero: **AI crop intelligence that makes uncertainty actionable.**
- AI Vision: **See what the crop image tells us.**
- EcoMind: **Add environmental context to the picture.**
- Safety: **Know when to act — and when to verify.**
- Impact: **No baseline, no invented savings.**
- Demo: **Synthetic demo result — not a live model prediction.**

## 14. Acceptance Criteria
- Product is understandable within the first viewport.
- AI Vision, EcoMind and Safety-first are immediately clear.
- DEMO MODE is visible when enabled.
- Low confidence visibly blocks recommendations.
- Moderate confidence clearly requests manual verification.
- Weather provenance is visible.
- Impact numbers never appear without baseline data.
- Desktop/tablet/mobile states are intentionally designed.
- Animation does not interfere with safety or readability.

## 15. Design Principle
**Beautiful enough to attract attention, simple enough for a farmer to understand, and transparent enough to build trust.**
