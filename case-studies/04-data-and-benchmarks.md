# Data that changed a client conversation

**Namastay · 2026 · SQL/BigQuery, Mixpanel, client-facing analysis**

Luxury hotels judge a booking engine on one question: is it converting? Most of my analysis work was making that question answerable fairly, then turning the answer into something a client could act on. Analyses like these supported **€218K ACV** of client accounts in the company's KPI sheet.

---

## 1. A fair benchmark: compare hotels to their price peers

**Problem.** Clients compared their conversion rate to a single platform average. But a €150/night hotel and a €1,500/night hotel live in different worlds: expensive stays get researched longer and booked less impulsively. A single average made luxury hotels look bad and budget hotels look great.

**Method.**
- Conversion defined explicitly as **bookings ÷ booking-engine opens × 100**.
- Pulled unique opens and purchases for 481 hotels from Mixpanel, joined average daily rate (ADR) from BigQuery, and cleaned to a **165-hotel set**.
- Split into four price tiers:

| Tier | ADR | Avg conversion | Hotels |
|---|---|---|---|
| Low | €0–200 | 5.90% | 10 |
| Mid | €200–500 | 2.63% | 79 |
| High | €500–1,000 | 1.67% | 55 |
| Ultra luxury | >€1,000 | 0.98% | 21 |

**Result.** For a 12-property US lifestyle hotel group, **every property beat its tier benchmark**: Mid 4.27% vs 2.63%, High 3.35% vs 1.67%, Ultra luxury 1.84% vs 0.98%. Delivered as a four-page branded PDF with the formula and tier logic spelled out, then reused for two other client groups. [Try the benchmark](https://arko1911.github.io/Arkoprava-Pal/adr-benchmark.html).

---

## 2. The gap was mobile, not the hotels

**Problem.** A French luxury hotel collection felt its conversion was weak. Four of its hotels sat below their tier average despite higher booking values.

**Finding.** Splitting by device told the story. **Mobile was 64% of visitors but only 34% of bookers**: 0.56% mobile conversion vs 1.91% on desktop. Desktop alone sat right at the tier average. The problem wasn't the hotels or the prices; it was mobile checkout.

**Recommendations, each with a monthly measure:**
1. Cut to 2–3 rates per room (too many options after room selection confused guests).
2. Turn on abandoned-booking emails: one recovered booking a week is worth ~€50–115K a year per hotel.
3. Fix mobile checkout first at the two hotels holding **~€870K of a €914K** total opportunity.

I also flagged things the client needed to know even though they weren't asked: a 12% group-wide decline in 2026 vs 2025, three conflicting booking totals in their own workbook, and missing payment data for two hotels.

---

## 3. When the client's number disagrees with yours

An ultra-luxury Mediterranean resort reported 0.79% conversion; our data showed **1.11%, about 13% above its tier average**. Rather than argue, I asked them to reconcile by **period and definition**: what counts as a visit, and over which dates. The same analysis showed 49% of their bookings came from mobile (vs ~30% or less at comparable properties) and ~50% of payments went through Apple Pay. Platform-wide, Apple Pay handles ~75% of completed payments, a figure now in Namastay's sales deck.

---

## 4. A feature that didn't work, and saying so

**Question.** Did adding a buy-now-pay-later option raise conversion?

**What I found** (BigQuery, two hotel groups, ~6 months before vs after):
- Overall conversion rose **36.75%**, the headline everyone wanted.
- But by payment method, guests who chose buy-now-pay-later completed only **23.14%** of the time, vs 62.29% for card and 83.01% for Apple Pay. The drop happened exactly at the hand-off from Namastay's flow to the provider's own interface.
- Average order value didn't rise; add-ons per reservation rose 31.19%.

**Conclusion:** the conversion rise was real but **not attributable** to the feature. The lesson that carried into later partnerships: any third-party hand-off mid-checkout is where guests leave. The pattern holds across Mixpanel boards: checkout-to-purchase is usually 50–83%, except through third-party hand-offs (8–23%).

---

## 5. Root-causing a "data isn't arriving" bug

A US resort that had migrated booking systems was returning no data. I traced it to a provider field that still pointed to the **old system in four separate places** in the payload; the hotel record hadn't changed since March and no new credentials existed. Along the way I documented four latent issues for engineering:
- a silent-failure risk if the flag were flipped while the old system still routed bookings;
- device tracking broken for every hotel on the old system, because a JSON array function was called on a string field;
- missing fallback branches in provider logic;
- a possible promo-code capture gap.

---

## 6. Cutting the analytics bill

Event volume hit **3.91M in January** against a plan covering far less. I audited events by usefulness and proposed removing ~2.88M a month (e.g. high-volume page events no analysis used), worth ~$577/month in overage, with a comparison of two cheaper alternatives.

**Skills:** SQL/BigQuery · Mixpanel · funnel analysis · benchmarking design · client communication · debugging data pipelines
