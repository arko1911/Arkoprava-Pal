# Mapping sales-to-billing and onboarding

**Namastay · 2026 · Process design across sales, customer success, engineering and finance**

## 1. Sales to billing: the process nobody had written down

**Situation.** A signed deal passed from sales to customer success to finance with no documented process. Invoices were raised manually from a Slack channel, trials had no fixed length, and the CRM tracked hotels, not what each hotel was paying for.

**The structural insight.** The thing that flows through the process isn't the hotel. It's the **subscription**: one contract line for one product. A single hotel can hold several paid products at different stages: one live and billing, one on trial, one blocked. Tracking the hotel hides all of that.

**What I designed.**
- **Map A:** the one-time journey from signature to billable, covering both new clients and upsells.
- A new CRM **Subscription object**: product, new client vs upsell, status, trial end, billable-from date, billing model, churn reason, CS owner. Money fields moved off the company record onto the subscription.
- **"Blocked" as a flag, not a status**, so a stalled subscription doesn't vanish from pipeline reporting.
- A **trial resolution sub-flow** (convert / extend / drop) with automatic mid-trial and 7-days-before tasks, since CS set trial lengths by hand.
- A billing rule: conversions bill from **trial end + 1 day**, not from go-live.

```mermaid
flowchart LR
    A[Deal signed] --> B[Subscription created]
    B --> C{Trial?}
    C -->|No| E[Implementation]
    C -->|Yes| D[Trial running]
    D --> T{Mid-trial / T-7 check}
    T -->|Convert| E
    T -->|Extend| D
    T -->|Drop| X[Churned + reason]
    E --> F[Live]
    F --> G[Billable from trial end + 1]
    G --> H[Finance invoices]
```

**Still open:** Map B, the recurring monthly billing cycle, isn't built yet.

---

## 2. Onboarding: signed hotel to live hotel

**Situation.** Getting a signed hotel live took **10 weeks on average** (best 3.5, worst 18). Sales, CS and engineering each saw their own part; nobody saw the whole.

**What I did.** Mapped the journey into **9 phases**, each with a time range and exit criteria, reviewed with two senior colleagues including my manager. Then I pulled real cases to locate where time actually went:

| Pain point | Evidence |
|---|---|
| Information asked twice | Payment credentials arrived ~1 week after kick-off; website contact ~12 days after |
| Slow hand-offs | 3–5 day gaps between sales hand-off and CS pickup |
| Kick-off lag | One hotel's kick-off came ~11 days after hand-off; website access took ~3 weeks |
| Payment-provider setup | One provider took ~4 weeks to issue a new credential |
| Booking-system gaps | Rate-visibility gaps on one system, missing add-on prices on another, mismatched room IDs on a third |
| Final bottleneck | Opening booking channels was consistently the last thing blocking go-live |

The nine phases, with the time range each one takes:

```mermaid
flowchart TD
    accTitle: Signed hotel to live hotel in nine phases
    accDescr: Phase 1, sales to customer-success handoff, 1 to 2 days. Phase 2, organise kick-off, 1 to 2 weeks. Phase 3, kick-off and first configurations, 1 to 2 weeks. Phase 4 has three parts. 4a, hotel web teams, 0 to 4 weeks. 4b, payment providers and third parties, 1 to 8 weeks. 4c, channel opening, 1 to 5 weeks. Phase 5, manual configuration checks, 1 to 2 days. Phase 6, testing sessions, non-US only, 0 to 2 weeks. Phase 7, pre-go-live checks, 0 to 2 weeks. Phase 8, go-live, 0 to 1 week. Phase 9, post-go-live, a follow-up call at 3 weeks. In total, best 3.5 weeks, average 10, worst 18.
    P1[1. Sales → CS handoff<br/>1–2 days] --> P2[2. Organise kick-off<br/>1–2 wks] --> P3[3. Kick-off & first configs<br/>1–2 wks]
    P3 --> P4
    subgraph P4[4. Three sub-phases]
      P4a[4a. Hotel web teams<br/>0–4 wks]
      P4b[4b. Payment providers & third parties<br/>1–8 wks]
      P4c[4c. Channel opening<br/>1–5 wks]
    end
    P4 --> P5[5. Manual config checks<br/>1–2 days] --> P6[6. Testing sessions, non-US only<br/>0–2 wks] --> P7[7. Pre-go-live checks<br/>0–2 wks] --> P8[8. Go-live<br/>0–1 wk] --> P9[9. Post-go-live<br/>3-week follow-up call]
```

**Future state: 16 proposed automations**, each tied to evidence and marked by whether it needs engineering. Examples: block a deal from closing without hand-off fields; auto-create a hand-off thread and task pack; record the kick-off and extract answers into the CRM; chase channel opening after 5 days; phase timers with a Monday digest.

---

## 3. Taking hotels live

The company KPI sheet attributes **€41.6K of live ACV** to my work:

| What went live | ACV |
|---|---|
| A hybrid-hotel brand's two-hotel launch, Paris and Vienna | €17,280 (€7,848 + €9,432) |
| A Mediterranean island resort | €4,860 |
| Four hotels in one UK hotel collection | €8,640 (€2,160 each) |
| Five Cart Abandonment upsells ([upsell programme](01-upsell-programme.md)) | €10,800 |
| **Total live** | **€41,580** |

That's **seven hotels taken live** plus five upsells. Five more hotels from the same resort group as the island resort are in process (€4,860 each).

For the Paris and Vienna launch I was the primary contact while my manager was away: daily updates, an issue tracker kept current, prioritised bug tickets and a live-testing log. I ran the booking-engine integration test suite of **195 cases**: passes went from **42 to 77** and failures from **14 to 7** over June–July, with issues, bugs and feature requests logged for engineering. One request, a marketing opt-in, shipped as a product change. Both properties went live in August 2026.

---

## 4. Small tools and documents that saved time

- **Live client map** for sales: diffed a new CRM export against the hard-coded hotel list, added 18 newly live properties and removed a duplicate, bringing it to **250+** hotels with a self-updating count. [Demo on synthetic data](https://arko1911.github.io/Arkoprava-Pal/hotel-map.html).
- **Contract to CRM:** extracted properties, room counts, legal entity, terms, contacts and notice periods from a signed contract into a colour-coded CRM import, flagging fields the contract didn't actually evidence.
- **Deeplink builder** covering SynXis (217), D-Edge (84) and Mews (18).
- **CRM-to-database hotel mapping** across 294 hotels.
- **January bug report by source system**, each issue tied to a Jira ticket.
- **Payment-link competitor matrix:** about 15 vendors compared across 15 capabilities.
- **Enhanced Multiproperty requirements** (map-provider criteria and a v2.1 destination search), with a **Mapbox Studio feasibility report**.
- **Custom map styling for hotel groups:** two hand-off routes for a group's own Mapbox style, plus a validation checklist for customer success and dev:

```mermaid
flowchart TD
    accTitle: Two hand-off routes for custom Mapbox styling, plus checklist
    accDescr: Route A, JSON download. A zip is downloaded from the Mapbox console, customer success extracts style.json, it goes to staging, then quality control, then production. Route B, a public style URL, which requires publishing the style to production. Both routes end at a customer-success and dev checklist. The style loads in preview, pins are visible at key zoom levels, contrast and readability hold, Namastay's map overlays are still present, attribution is not hidden, and the token is domain-restricted with minimum scopes.
    subgraph A[Route A: JSON download]
      A1[Zip downloaded from Mapbox console] --> A2[CSM extracts style.json] --> A3[Staging] --> A4[QC] --> A5[Production]
    end
    subgraph B[Route B: public style URL]
      B2[Public style URL<br/>requires publishing to production]
    end
    A5 --> K
    B2 --> K
    K[CSM + Dev checklist:<br/>style loads in preview<br/>pins visible at key zoom levels<br/>contrast and readability<br/>Namastay overlays still present<br/>attribution not hidden<br/>token domain-restricted, minimum scopes]
```

**Skills:** process mapping · data modelling · cross-functional alignment · root-cause analysis · implementation management
