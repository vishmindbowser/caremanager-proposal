# Feature rollup — internal review only

Not part of the client-facing proposal. Maps each client-friendly feature group in the
proposal back to the source rows in `input/CareManager_Estimates.xlsx`, so you can check
nothing was mis-summarized before this goes to Amy Lever. No hours or costs are repeated
here — cross-check those directly in the workbook if needed.

## Proposal §04 "What we would build" / §09 "Phase 1 scope, by role"

| Proposal group | Excel sheet | Excel rows rolled up |
|---|---|---|
| Identity & Family Circle | Phase 1 - Web Patient | Auth — sign up/in/verify/reset; Account — get/update, sign out; Registration screen 2 / Invitation claim; Profiles — switcher, add/manage, deactivate/activate |
| Identity & Family Circle (data sharing) | Phase 1 - Web Patient | Data Sharing — shared with others / with me / caregiving |
| Personal Health Record | Phase 1 - Web Patient | Profile — Overview (About); Profile — Emergency Contacts; Profile — Medical Documentation; Health Record — Insurance; Care Team (Practitioners/Pharmacies/Facilities); Medications & Supplements; Allergies & Sensitivities; Vaccinations; Medical History; Family History; Social History; Life Events; Surgeries; Office Visits; Laboratory; Imaging; Hospitalizations; Other Procedures; Other Documents; Medical Devices; Behavioral Health; Medical Aesthetics |
| Care Coordination | Phase 1 - Web Patient | Dashboard; Tasks; Appointments; Document Inbox; Notification Service; Notifications |
| Account tools | Phase 1 - Web Patient | Settings — prompt schedules/notification prefs; Help Center; Export (PDF/CSV); Manage Plan Users |
| Mobile Experience | Phase 1 - Mobile Patient | All rows (mirrors Web Patient feature-for-feature) plus: Camera / photo / file capture; Connected Apps — Apple Health / Google Fit; Settings — Login and Security; Shell — tab bar, More list, Quick Add |
| Platform Operations (Super Admin) | Phase 1 - Super Admin | Auth; Shell/session chrome; Dashboard — Home; Client Accounts; Notifications; Settings; Library — Dropdown Option Lists; Library — Help Centre FAQs; Library — Legal Document Metadata; Library — Reminder Templates |
| Security & Compliance Foundation / DevOps-Platform | Phase 1 and 2 - DevOps | All "Phase 1" rows: network/services architecture; Dev/QA/Stage IaC; Prod IaC; CI/CD for IaC, FE, BE, mobile; Keycloak multi-tenancy setup; file-scanning pipeline (Yara+ClamAV); logging/monitoring/alerting/status page; SecOps pipeline; Prowler infra scanning; pentesting; compliance verification; developer support |

## Proposal §06 "Architecture and integrations"

Sourced from the "Tech Stack" note block in `Phase 1 and 2 - DevOps`: Mobile App = React
Native (TypeScript); Backend = Node; FE (Patient, Super Admin) = React JS (TypeScript);
Authentication service = Keycloak (hosted); Infra services = Authentication, Document,
Notifications (via providers), Schedulers, Observability, payments (Stripe), RDS, S3;
Compliance = HIPAA.

## Proposal §10 "Phase 2 scope"

| Proposal group | Excel sheet | Excel rows rolled up |
|---|---|---|
| Insights | Phase 2 | Web Patient → Insights |
| Goals | Phase 2 | Web Patient → Goals; Mobile → Goals |
| Resources | Phase 2 | Web Patient → Resources; Mobile → Resources |
| Trackers (folded into Insights framing, not named separately in the proposal) | Phase 2 | Web Patient → Trackers — integrations & readings |
| Events & programs | Phase 2 | Web Patient → Events & Programs; Mobile → Events & Programs |
| Journals | Phase 2 | Web Patient → Journals; Web Patient → Settings – Journal Settings; Mobile → Journals |
| Subscription & billing (patient side) | Phase 2 | Web Patient → Billing & Subscription; Mobile → Billing & Subscription |
| Subscription Plans & Services | Phase 2 | Super Admin → Subscription Plans & Services |
| Billing visibility | Phase 2 | Super Admin → Billing & Payment Visibility — Stripe sync |
| Platform Users | Phase 2 | Super Admin → Platform Users |
| Resource library & events management | Phase 2 | Super Admin → Library — Resource Library; Super Admin → Events & Programs |

## SOW notes carried into the proposal

- **Care Coordinator (CareManager CSM)** — SOW note #4. Proposal §09 includes it as a
  short "noted for later" callout, not as a built feature, per your instruction to
  mention it only as a note.
- **Caregiver model** — SOW note #5. Reflected in "Identity & Family Circle" as
  family/caregivers added through the standard patient flow (Phase 1); the verified
  professional-caregiver tier (future phase) was **not** mentioned in the client-facing
  proposal, to keep that section simple — flag if you want it added back as a roadmap note.

## Deliberately excluded from every output

- All hour figures and the internal DevOps hour discrepancy (444 vs 420 hrs Phase 1;
  116 vs 20 hrs Phase 2 — see the workbook's `Phase 1 and 2 - DevOps` sheet vs. its own
  `Efforts Summary` roll-up) — you asked to ignore/omit hours entirely, so this was not
  reconciled and does not appear anywhere.
- The design-prototype links and plaintext passwords in `Efforts Summary` (rows near the
  bottom of that sheet) — excluded from both the proposal and this file as a matter of
  not distributing credentials in a client-facing artifact.

## Assumptions made that are not literally in the Excel or your instructions

These were reasonable defaults, not "facts" — flag any you want changed:

- Proposal date: September 28, 2026 (today). Version 1.0. Validity: 30 days.
- Phase 1 milestone *content* groupings (M1–M7 build themes) are Mindbowser's own
  sequencing logic, built from the Excel's feature list — the Excel does not prescribe
  an order.
- Phase 2 payment split (34% / 33% / 33%) — you specified the Phase 1 split (Kickoff 20%,
  remaining 8 milestones at 10% each); Phase 2's split was not specified, so an even
  three-way split was used.
- "Ongoing retainer" and "SOC 2/GDPR extendable by agreement" language — standard
  Mindbowser offering boilerplate, not confirmed pricing or scope for this engagement.
  Both are flagged with `[[TO CONFIRM]]` inline in the HTML/PDF.

## Revision 2 — Phase 1 focus (2026-09-29)

Per your follow-up request, the proposal was narrowed to Phase 1 only:

- Proposal date updated to September 29, 2026. Status line shortened to "Proposal for
  review" (dropped the "indicative plan, firm milestones below" trailer).
- Hero logo replaced with the supplied Mindbowser "W" mark (`output/assets/mindbowser-mark.png`,
  cropped from the file you attached) plus the "Mindbowser" wordmark next to it.
- Phase 2 collapsed from a full role-based scope section (§10) into one brief section:
  three module groups (Patient engagement / Monetization & admin / Production resilience)
  plus two stat tiles (~1.5 mo, USD 42,868), explicitly marked "indicative only — not part
  of this proposal's milestone plan or Phase 1 total."
- Gantt chart, milestone list, and the investment section (§13) are now Phase 1 only —
  9 milestones, W1–W18, USD 135,057. Phase 2's Hypercare/P2 rows were removed from the
  Gantt entirely, not just hidden.
- Added an "Indicative, confirmed at M0" callout directly above the Gantt (§11), since
  you asked for the milestones to be explicitly flagged as subject to change at Kickoff.
- Support model changed: previously "1-week hypercare + optional paid retainer" is now
  "1 month complimentary bug-fix support after delivery on UAT or equivalent, then a paid
  maintenance & support plan." Reflected in §13's stat tile, §14's support cards, and
  §12's cadence list.
- HIPAA language rewritten throughout (§04, §07, §08, §09): CareManager's platform is
  built **HIPAA-ready**; formal **HIPAA certification** is CareManager's own compliance
  process (e.g. via Sprinto or similar, plus a third-party audit), which Mindbowser
  supports but does not itself certify. Mindbowser's own SOC 2 Type II (a company-level
  credential, unrelated to CareManager's certification) is now explicitly called out as
  a separate fact in §07 to avoid the two being conflated.
- DevOps split across phases made explicit: §08 now has a callout stating Phase 1 covers
  the single-AZ HIPAA-ready foundation (CI/CD, multi-tenant identity, security gates),
  while Multi-AZ resilience and disaster recovery are Phase 2 scope (source: the `Phase 2`
  rows in the `Phase 1 and 2 - DevOps` Excel sheet — Multi-AZ infra setup, DR setup, DR
  drill + fixes). Same split echoed in §09's DevOps bullet and §10's "Production
  resilience (DevOps)" module.
