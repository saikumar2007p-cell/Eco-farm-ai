# EcoFarm AI — Technical Architecture & Technology Stack v1.0

## Executive Recommendation
Use a two-surface architecture: **Framer** for the public marketing/brand experience and a dedicated **Next.js** application for the authenticated, AI-heavy product experience.

## Recommended Stack
| Layer | Technology | Role |
|---|---|---|
| Marketing | Framer | Public website, landing pages, content |
| Product app | Next.js + React + TypeScript | Authenticated AI workflow |
| UI | Tailwind CSS + shadcn/ui | Reusable accessible components |
| Animation | Motion / Framer Motion | Product interactions |
| Backend | Next.js server layer + Supabase Edge Functions | Secure application logic/integrations |
| Database | Supabase PostgreSQL | Users, analyses, provenance, configuration |
| Auth | Supabase Auth | Identity and roles |
| Storage | Supabase Storage | Crop images/assets |
| AI Vision | Gemini initially | Image analysis/reasoning |
| Weather | OpenWeather initially | Environmental context |
| Hosting | Vercel + Framer | Application + marketing deployment |
| Analytics | PostHog or equivalent | Product usage/funnels |
| Monitoring | Sentry or equivalent | Errors/performance |
| Source control | GitHub | Code/reviews/CI |
| CI/CD | GitHub Actions | Automated test/build/deploy |

## High-Level Architecture
**Public:** User → Framer → marketing/content pages.

**Application:** User → Next.js → authenticated UI → server/API layer → Supabase / AI / weather services.

**Data:** Crop image → secure storage → AI analysis → structured result → confidence/safety policy → database → user-facing analysis.

Third-party API secrets must remain server-side and must never be exposed in browser code.

## Frontend Routes
- `/` — marketing homepage
- `/how-it-works` — product explanation
- `/safety` — safety philosophy
- `/insights` — public content
- `/app` — authenticated product shell
- `/app/dashboard` — dashboard
- `/app/analyze` — crop analysis
- `/app/analysis/[id]` — saved analysis
- `/app/history` — analysis history
- `/app/profile` — account settings
- `/app/review/[id]` — future expert review

## AI Analysis Pipeline
1. Upload crop image.
2. Validate image quality/type.
3. Store securely.
4. Call AI Vision server-side.
5. Produce structured evidence.
6. Evaluate confidence.
7. Apply authoritative safety gate.
8. Enrich with weather/context.
9. Calculate EcoMind.
10. Determine recommendation state.
11. Persist result and provenance.
12. Render the result.

## Safety Architecture
The safety engine sits between AI output and the user-facing recommendation:

`AI output → Confidence validation → Safety policy → Recommendation state`

- Low confidence: block recommendation.
- Moderate confidence: require manual verification.
- Permitted state: show evidence, confidence, provenance, and limitations.

The UI must not be able to bypass the safety state.

## Proposed Database Schema
- `profiles` — user identity/profile
- `analyses` — one crop analysis
- `analysis_inputs` — image/context metadata
- `analysis_results` — structured AI output
- `weather_records` — weather provenance
- `ecomind_results` — EcoMind output/version
- `impact_baselines` — baseline inputs
- `impact_results` — deterministic impact calculations
- `reviews` — human verification
- `audit_events` — traceability

Enable Row Level Security for user-owned data and role-based access for expert/admin workflows.

## Roles
**Farmer:** create analyses, upload images, provide context, view own results.

**Agricultural expert:** review assigned analyses, record verification decisions, add notes.

**Admin:** manage users, configuration, content, safety policies, and operations.

**System/service:** execute AI/weather/calculation jobs and audit metadata.

## Proposed APIs
- `POST /api/analyses`
- `GET /api/analyses/{id}`
- `POST /api/analyses/{id}/run`
- `GET/POST /api/weather`
- `POST /api/ecomind`
- `POST /api/impact`
- `POST /api/reviews/{id}`
- `GET /api/provenance/{id}`

Exact schemas, rate limits, error codes, and production SLAs remain TBD.

## Security Requirements
- Keep AI/weather secrets server-side.
- Use Auth and RLS.
- Audit privileged actions.
- Validate file type and size.
- Rate-limit expensive AI operations.
- Enforce role checks.
- Protect private crop images.
- Define retention/deletion policy before production.

## Deployment
- Marketing: Framer.
- Application: Next.js on Vercel or equivalent.
- Backend: Supabase Postgres/Auth/Storage/Edge Functions.
- Source: GitHub.
- CI/CD: automated lint/test/build/deploy.
- Environments: local → development → staging → production.

## Testing
- Unit: safety rules, confidence mapping, impact calculations, schema validation.
- Component: upload, confidence, safety states, analysis cards.
- Integration: AI, weather, Supabase, Auth.
- E2E: upload → analysis → safety gate → result.
- Security: authorization, RLS, file access, secret handling.
- Model evaluation: accuracy, confidence quality, edge cases, expert agreement.

## Development Phases
0. Preserve current prototype and acceptance tests.
1. Build design system and Next.js shell.
2. Connect Supabase Auth, DB and Storage.
3. Move AI Vision into secure server-side architecture.
4. Add weather provenance and EcoMind.
5. Implement safety engine and human review.
6. Add analytics, monitoring, tests and CI/CD.
7. Agricultural validation and controlled pilot.
8. Production hardening and launch.

## Final Architecture Decision
**Framer + Next.js + Supabase**, with AI and weather services accessed from secure server-side code.

Keep the architecture deliberately simple at first. Add queues, dedicated Python services, Kubernetes, or specialized infrastructure only when real workload, model complexity, or scale requires them.
