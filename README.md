# Arkoprava Pal - Product & Strategy

I turn messy commercial questions into decisions: who to talk to, what the data actually says, what to build or kill, and how to get it signed. Since January 2026 I've done this as Product & Strategy Manager at **Namastay**, a Paris hotel-tech startup whose direct-booking engine runs on 250+ live luxury and boutique hotels. Before that: actuarial model validation for a London consultancy and EU programme evaluation in Belgium.

![SQL](https://img.shields.io/badge/SQL-analysis-336791)
![BigQuery](https://img.shields.io/badge/BigQuery-SQL-4285F4)
![Mixpanel](https://img.shields.io/badge/Mixpanel-funnels-7856FF)
![Python](https://img.shields.io/badge/Python-scraping_%26_validation-3776AB)
![Power BI](https://img.shields.io/badge/Power_BI-IFRS_17_reporting-F2C811)
![Attio](https://img.shields.io/badge/Attio-CRM-1F2937)
![Mailchimp](https://img.shields.io/badge/Mailchimp-campaigns-FFE01B)
![Figma](https://img.shields.io/badge/Figma_%26_FigJam-flows_%26_maps-F24E1E)
![Notion](https://img.shields.io/badge/Notion-docs-000000)
![Looker](https://img.shields.io/badge/Looker-4285F4)
![Google Analytics](https://img.shields.io/badge/Google_Analytics-E37400)
![Jira](https://img.shields.io/badge/Jira-tickets-0052CC)
![Salesforce](https://img.shields.io/badge/Salesforce-CRM-00A1E0)
![Claude](https://img.shields.io/badge/Claude_%26_Claude_Code-AI_tools-D97757)

> **Confidentiality:** Namastay is named; its hotel clients and commercial partners are anonymised by type and size, never by name. Every figure is real and comes from my own analyses or the company KPI sheet. The demos run on synthetic data. Integration platforms and tools (SynXis, Mews, Mixpanel, BigQuery) are named because they are public products.

---

## Impact at a glance

| | |
|---|---|
| **€117K** | attributed to my work in the company KPI sheet: €41.6K ACV live, a €50K partner integration bonus received, €25.5K ACV in process |
| **€218K ACV** | of existing client accounts supported or retained by analyses I ran; the largest line, €80,040, came from an upsell on/off experiment |
| **+141%** | revenue for one hotel client, first vs second half on Namastay ($477K → $1.15M) |
| **7 of 8** | sales/CS colleagues backed the upsell I picked after interviewing all of them |
| **€275K** | recovered-revenue proof case that unblocked the upsell pitch |
| **4 partnerships** | scoped and evaluated; two led end to end, one deliberately killed |

---

## Live demos

Three working tools, rebuilt on synthetic data so they run in the browser with nothing confidential in them.

| Demo | What it shows |
| --- | --- |
| [**Cart-abandonment calculator**](https://arko1911.github.io/Arkoprava-Pal/cart-abandonment.html) | How much revenue abandoned-booking emails recover for a hotel, the model behind the upsell pitch |
| [**ADR-tier benchmark**](https://arko1911.github.io/Arkoprava-Pal/adr-benchmark.html) | Why comparing a €1,500/night hotel to a €150/night one is wrong, and what a fair benchmark looks like |
| [**Client world map**](https://arko1911.github.io/Arkoprava-Pal/hotel-map.html) | The live-client map I built for the sales team, filterable by region and booking system |

---

## How I work

1. **Find the real blocker before pitching a fix.** The upsell problem wasn't the pitch, it was proof. The onboarding problem wasn't speed, it was information asked twice.
2. **Benchmark against the right peer group.** Averages across different price points hide more than they show.
3. **Killing an option is a result.** A partnership that doesn't fit the distribution model is cheaper to drop in week two than in month six.
4. **Write it down so others can run it.** Requirements, scoring tables and process maps are built to be reused, not to be presented once.

---

## Projects

| # | Project | What it proves | Links |
| --- | --- | --- | --- |
| 1 | Building an upsell motion from zero | Finding the real blocker (proof, not pitch) and building a motion the team can repeat | [case study](case-studies/01-upsell-programme.md) · [live demo](https://arko1911.github.io/Arkoprava-Pal/cart-abandonment.html) |
| 2 | Partnerships: what to build, what to kill | Business cases that end in a decision, including a no | [case study](case-studies/02-partnerships.md) |
| 3 | Mapping sales-to-billing and onboarding | Writing down a cross-team process nobody owned, then fixing it with evidence | [case study](case-studies/03-process-design.md) · [live demo](https://arko1911.github.io/Arkoprava-Pal/hotel-map.html) |
| 4 | Data that changed a client conversation | Fair benchmarks and honest attribution, turned into client action | [case study](case-studies/04-data-and-benchmarks.md) · [live demo](https://arko1911.github.io/Arkoprava-Pal/adr-benchmark.html) |
| 5 | Discovery: experiences, not just rooms | Research, journeys and a workshop that ended in agreed actions | [case study](case-studies/05-discovery.md) |
| 6 | Before Namastay | Checking numbers are right before anyone makes decisions with them | [case study](case-studies/06-before-namastay.md) |
| 7 | A self-serve coupon dashboard, written as a PRD | Scoping a v1 that can ship, with v2 and v3 already specified | [case study](case-studies/07-coupon-dashboard-prd.md) |
| 8 | Impact and analytics | Where the €218K comes from, client by client | [case study](case-studies/08-impact-and-analytics.md) |

### 1. Building an upsell motion from zero → [case study](case-studies/01-upsell-programme.md)

Namastay had several paid features most hotels weren't using, and no upsell process. I interviewed all eight sales and customer-success colleagues: Cart Abandonment won 7 of 8 votes, and every interview named the same blocker, which was no proof it worked. I built that proof from live client data (2,285 recovery emails, 200 bookings recovered, €274,998), merged two messy exports into a 153-hotel target list, and built the campaign assets. **5 hotels signed Cart Abandonment upsells (€10.8K ACV)**, with one more in process.

### 2. Partnerships: what to build, what to kill → [case study](case-studies/02-partnerships.md)

Four partnerships, each a bet on putting more of the guest's spend inside the booking flow. **Refund protection:** the incumbent's data showed €16,106 of protection sold but only €322 reaching Namastay; I built a three-scenario business case, a 40-property launch list and 44 requirements, and led the negotiation call and sign-off alongside leadership. **The €50K integration bonus has been received.** **Restaurant booking:** led v1 and v2, prioritised v2 with RICE and removed 17 duplicate requirement rows. **Spa:** a ten-factor build-vs-embed framework; v1 scoped to appointments. **eSIM:** recommended deprioritising, because the provider's proven distribution was airlines and travel agencies, not hotels.

### 3. Mapping sales-to-billing and onboarding → [case study](case-studies/03-process-design.md)

What flows from signature to invoice isn't the hotel, it's the **subscription**, so I designed a CRM Subscription object with a trial sub-flow and a billing rule. Onboarding took 10 weeks on average (best 3.5, worst 18); I mapped it into 9 phases, located where time actually went, and proposed 16 automations tied to evidence. **€41.6K of live ACV** is attributed to my work: seven hotels taken live (a two-hotel Paris and Vienna launch, a Mediterranean island resort, and four hotels in one UK collection) plus five Cart Abandonment upsells, with five more hotels from the same resort group in process.

### 4. Data that changed a client conversation → [case study](case-studies/04-data-and-benchmarks.md)

A **165-hotel, four-tier ADR benchmark** so hotels are compared with their price peers; for a 12-property US group, every property beat its tier. For a French luxury collection, the gap was mobile (64% of visitors, 34% of bookers), not the hotels. A buy-now-pay-later launch coincided with a 36.75% conversion rise that the data showed **wasn't attributable** to the feature. Also: a root-caused missing-data bug and an analytics-event audit worth ~$577/month. Analyses like these supported **€218K ACV** of client accounts.

### 5. Discovery: experiences, not just rooms → [case study](case-studies/05-discovery.md)

Tested the idea that guests book a stay while engines sell a room: a market map, a portfolio scan (only 55% of hotels surfaced dining, 32% spa), client interviews, a 12-property audit and length-of-stay data across 313,494 bookings. Designed multi-hotel itinerary flows, and designed a payments-onboarding workshop (my manager oversaw it) that surfaced 20 problems and agreed actions, supported by a 351-gateway matrix.

### 6. Before Namastay → [case study](case-studies/06-before-namastay.md)

**AInsurCo** (London, remote; two engagements): validated a rebuilt Python life-insurance pricing model against legacy Excel/VBA, with 2,716 of 2,797 cases matched (97.1%) and every one of the 81 mismatches traced; built IFRS 17 reporting in Power BI; reconciled 74 pension test cases. **ADE** (Louvain-la-Neuve): part of the team that presented an EU education evaluation at the European Parliament; wrote a full Nigeria country case study; mapped 624 EU actions; screened 1,314 climate projects. M.Sc in Management, Emlyon Business School, where I led a team building a market-entry strategy for **Air Liquide's hydrogen energy initiative** (presented to its Director of Hydrogen Energy) and, as International Head, organised International Week and Welcome Week for 200+ students from 16+ nationalities.

### 7. A self-serve coupon dashboard, written as a PRD → [case study](case-studies/07-coupon-dashboard-prd.md)

Hotels needed a customer-success manager every time they wanted a coupon or group code. I wrote a **five-sheet requirements workbook** (dashboard, templated CSV, raw CSV, update logic, column mapping) and made the scoping calls: **SynXis only for v1**, **manual entry in v1 and CSV upload in v2**, the **coupon code as the only dedup key** (case-insensitive, trimmed) and one login per hotel. That gave 40 requirements for v1, 22 for v2 and 26 for v3.

### 8. Impact and analytics → [case study](case-studies/08-impact-and-analytics.md)

The breakdown behind the €218K, client by client. For one hotel client, **revenue rose 141% ($477K → $1.15M)** and reservations more than doubled (166 → 336) from the first to the second half on Namastay. An upsell experiment (on at 3 hotels, off at 10) showed 3,982 displays → 873 selections (~22%). A 10-hotel group's €36.7M, 14,101-booking retention analysis showed its 2026 drop was its own, not the market's. Across the whole platform, 7.58M opens led to 122K purchases (~1.6%).

---

## Back office

Smaller tools and documents ([details](case-studies/03-process-design.md#4-small-tools-and-documents-that-saved-time)):

- A deeplink builder covering SynXis (217), D-Edge (84) and Mews (18), plus a CRM-to-database mapping of 294 hotels
- A January bug report by source system, each issue tied to a Jira ticket
- A payment-link competitor matrix: about 15 vendors × 15 capabilities
- Enhanced Multiproperty requirements and a Mapbox Studio feasibility report
- A 19 March brainstorm and an opportunity–solution tree for experience bookings, plus a trend scan of 32 hotels' itineraries ([discovery](case-studies/05-discovery.md))

---

## Contact

Open to product, strategy and data roles. Based in Paris and open to relocating (for example Berlin or Amsterdam).

Arkoprava Pal · 📍 Paris · ✉️ [palarko19@gmail.com](mailto:palarko19@gmail.com) · 🔗 [LinkedIn](https://linkedin.com/in/arkoprava-pal) · 🌐 [arko1911.github.io](https://arko1911.github.io/)
