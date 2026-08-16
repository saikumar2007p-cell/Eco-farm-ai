# EcoFarm AI — Full Product Requirements Document v2.0

## Product Vision
Make agricultural AI more useful by making its uncertainty visible and actionable.

**Core message:** “We don't hide uncertainty; we make it actionable.”

## Product Principles
- Safety before automation.
- Evidence before recommendation.
- Transparency before confidence.
- Human verification when uncertainty matters.
- Provenance for external information.
- No invented numbers.
- No unsupported scientific/agronomic validation claims.

## Target Users
**Farmers:** understand crop condition and know when to act or verify.

**Agricultural experts:** review AI-assisted findings using evidence, confidence, provenance, and recommendation state.

**Evaluators/judges:** understand the product differentiation quickly through the demo flow.

## Core Workflow
Entry → Crop Image + Field Context → Analysis → Evidence → Confidence → Weather/Provenance → EcoMind → Safety/Action.

## Product Scope
- AI Vision crop-image analysis.
- Field context.
- Model-reported confidence.
- Confidence-aware safety controls.
- EcoMind environmental/contextual scoring.
- Weather information with provenance.
- Safety & Provenance panel.
- Baseline-protected impact calculations.
- Visible DEMO MODE and synthetic-result disclosure.
- Future production auditability and human review.

## Functional Requirements
| ID | Requirement | Priority |
|---|---|---|
| FR-001 | Visible DEMO MODE when enabled | High |
| FR-002 | Synthetic results clearly disclosed | High |
| FR-003 | Accept valid crop image | High |
| FR-004 | Allow field context | High |
| FR-005 | Produce structured analysis card | High |
| FR-006 | Display model-reported confidence | High |
| FR-007 | Low confidence blocks recommendation | Critical |
| FR-008 | Moderate confidence requires manual verification | Critical |
| FR-009 | Do not call confidence a calibrated probability without validation | Critical |
| FR-010 | Show weather/environment provenance | High |
| FR-011 | Label EcoMind treatment profiles as prototype assumptions until validated | Critical |
| FR-012 | Missing baseline prevents invented savings/impact | Critical |
| FR-013 | Provide Safety & Provenance panel | High |
| FR-014 | Communicate differentiation | Medium |
| FR-015 | Production traceability | High / Proposed |
| FR-016 | Human review workflow | High / Proposed |

## Confidence Policy
- **Low confidence:** block the recommendation.
- **Moderate confidence:** require manual verification.
- **Permitted recommendation state:** show result with evidence, confidence, provenance, and limitations.

Exact numerical thresholds are **TBD** and require model evaluation and agricultural validation.

## AI Vision
AI Vision interprets an uploaded crop image and produces structured crop evidence. Production design should include input validation, model/version metadata, structured evidence, confidence state, limitations, and provenance.

## EcoMind
EcoMind is a contextual environmental scoring layer. Until scientifically/agronomically validated, scores and treatment profiles must remain explicitly labeled as prototype assumptions.

## Weather & Provenance
Environmental data should show source/provider and timestamp. Production data freshness, geographic precision, caching, fallback behavior, and approved providers remain TBD.

## Impact Calculations
Impact/savings calculations must be deterministic and baseline-backed. If the required baseline is missing, return `not_available` rather than estimating a number.

## Safety UX
Safety should be visible in the main interface. Low confidence is blocked; moderate confidence requires verification; permitted results include limitations; missing baseline prevents quantitative impact; demo mode discloses synthetic results.

## Proposed Production Data
A production analysis should be traceable to input image/context, model version, confidence state, weather provenance, EcoMind version, recommendation state, reviewer state, and audit identifiers.

## Security & Privacy — Proposed
Define authentication/authorization, secure image handling, encryption, retention/deletion, access logging, secrets management, API-key protection, rate controls, and privacy/legal review before production.

## Non-Functional Requirements — Proposed
Define targets for performance, availability, scalability, reliability, observability, accessibility, localization, and per-analysis cost.

## Error Handling
- Invalid image → explain and request a supported image.
- Low-quality image → request a clearer image.
- Missing context → explain the limitation or request required input.
- Low confidence → block recommendation.
- Moderate confidence → require manual verification.
- Weather unavailable → defined fallback behavior.
- Missing baseline → no invented impact.
- External API failure → clear error/fallback.
- Unsupported crop/condition → explicit out-of-scope behavior.

## Analytics — Proposed
Track analysis completion, low-confidence rate, manual verification rate, recommendation actions, expert agreement, data completeness, and safety incidents.

## Release Strategy
**Release 0:** hackathon prototype with DEMO_MODE and offline demo behavior.

**Release 1:** controlled validation with agricultural datasets, expert review, confidence evaluation, and EcoMind validation.

**Release 2:** controlled pilot with monitoring, support, feedback, and human oversight.

**Release 3:** production only after model, safety, security, privacy, governance, and operational readiness gates pass.

## Hackathon Demo
1. Open app and point to DEMO MODE.
2. Upload crop image and enter field context.
3. Run analysis and show structured crop evidence.
4. Explain model-reported confidence and that it is not a calibrated probability.
5. Show weather provenance and EcoMind.
6. Show prototype-assumption notice and Safety & Provenance panel.
7. Show that impact numbers appear only with baseline data.
8. Close with: **“We don't hide uncertainty; we make it actionable.”**

## Acceptance Tests
- Backend smoke tests pass.
- Application starts and is reachable.
- DEMO MODE is visible.
- Valid image produces crop-analysis card.
- Low confidence blocks recommendation.
- Moderate confidence requires verification.
- Weather provenance is visible.
- Missing baseline produces no invented savings/impact.

## Roadmap
1. Prototype / hackathon.
2. Agricultural validation.
3. Controlled pilot.
4. Production.

## Open Decisions
- Initial crops and conditions in scope.
- Numerical confidence thresholds.
- Confidence calibration methodology.
- Validation datasets.
- Agricultural validation authority.
- EcoMind scoring methodology.
- Approved weather sources.
- Minimum impact baselines.
- Production latency/availability/cost targets.
- Privacy/security/retention requirements.
- Languages/accessibility.
- Human-review escalation and audit process.
- Public claims about accuracy/outcomes.

## Final Product Definition
EcoFarm AI is a safety-first AI agricultural decision-support product combining crop-image analysis, field context, environmental information, EcoMind scoring, confidence-aware recommendation controls, and transparent provenance. It should make uncertainty visible, block low-confidence recommendations, require verification where appropriate, and avoid unsupported quantitative impact claims.

**Production gate:** do not claim scientific or agronomic validation until validated with appropriate agricultural data.
