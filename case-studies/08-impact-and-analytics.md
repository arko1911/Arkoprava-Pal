# Impact and analytics: what the numbers did for clients

**Namastay · 2026 · Mixpanel, BigQuery and client reports**

The company KPI sheet links my analyses to **€217,812 ACV of client accounts supported or retained** (the €218K headline). This page shows where that number comes from, starting with the strongest single result. Clients are described by type and size; every figure comes from my own analyses or the KPI sheet.

| Client (anonymised) | ACV supported / retained | Analysis |
|---|---|---|
| A hotel group running an upsell experiment | €80,040 | [Upsell on vs off](#2-the-upsell-experiment) |
| A 12-property US lifestyle hotel group | €54,480 | [Tier benchmark](04-data-and-benchmarks.md) and [funnel review](#4-a-funnel-review-after-a-calendar-change) |
| A 10-hotel group at churn risk | €43,332 | [Retention analysis](#3-a-retention-analysis-whose-drop-was-it) |
| A high-ADR property | €14,400 | [Revenue report](#1-client-impact-reports) |
| An ultra-luxury hotel brand | €12,600 | [Reconciling conversion](04-data-and-benchmarks.md) |
| Three smaller properties | €5,400 · €5,400 · €2,160 | [Funnel reports](#1-client-impact-reports) |
| **Total** | **€217,812** | |

---

## 1. Client impact reports

**The featured result: revenue +141%.** For one hotel client, I compared the first and second halves of its time on Namastay:

| Metric | First half | Second half | Change |
|---|---|---|---|
| Revenue | $477K | $1.15M | **+141.34%** |
| Reservations | 166 | 336 | **+102.41%** (more than doubled) |
| Add-on revenue | | | **+60.48%** |
| Average basket | $2,875 | $3,428 | **+19.23%** |

Upsells over January–June went from 13 to 46.

**A hotel's conversion, year on year.** Another client's conversion rose **30.31%** in 2026 vs 2025, and 32.8% in its first month on Namastay. Its three-month average went from 6.85% for the first three months to 8.52% for the last three.

**A report on $1.17M of revenue.** For a high-ADR property I built the revenue picture from BigQuery: **$1,168,358** of revenue from 165 bookings and 651 room nights, an ADR of $1,794.71, an average stay of 3.95 nights and a 79-day booking window. From May to August 2026, the monthly basket ranged from $4.4K to $8.3K and lead time from 62 to 112 days. In Mixpanel, 17.82K date selections led to 156 purchases (0.88%). One rule I held: no "mobile has increased" claim without a pre-launch baseline.

**Three smaller properties**, each with its own funnel:

| Property | Window | Funnel | Conversion |
|---|---|---|---|
| A | 12 months | 43.42K opens → 549 purchases | 1.26% |
| B | 19 Aug – 19 Oct 2026 | 18.18K opens → 213 purchases (French-language dashboard) | 1.17% |
| C | After Apple Pay went live | 225 checkouts → 130 purchases | 57.78% checkout → purchase |

---

## 2. The upsell experiment

One hotel group had upsells **switched on at 3 hotels and off at the other 10**. In the Mixpanel board for the experiment (since 1 April 2026), **3,982 upsell displays led to 873 selections, about 22%**. In the second half of 2025, guests added an add-on 538 times and removed one 50 times. This analysis is the largest line in the €218K: **€80,040 ACV supported or retained**.

---

## 3. A retention analysis: whose drop was it?

A **10-hotel group** was unsure about Namastay's performance and at risk of churning. The scale: **€36.7M of revenue across 14,101 bookings**, 52,867 room nights, a €695 ADR and 1.21% conversion. Bookings had grown **89%** from Q2–Q3 2024 to Q2–Q3 2025.

- **Peers matched by hotel type, not just price.** Each underperforming hotel was compared with core-peer medians (for one hotel, an ADR of €414 against a peer median of €327).
- **2025 vs 2026 vs peers.** The decline was the group's own: peers improved over the same period, so it wasn't the market or the season.
- **Where it broke.** At the group's ski hotels, the funnel broke at the date-selection step.
- The mobile gap and the €914K opportunity from the same analysis are in [Data that changed a client conversation](04-data-and-benchmarks.md).

Result: **€43,332 ACV supported or retained**.

---

## 4. A funnel review after a calendar change

After an August calendar change, the 12-property US lifestyle group asked for a funnel review at its weaker hotels. I built five-step funnels (open → calendar → room → checkout → purchase) per property:

| Property | Window | Conversion |
|---|---|---|
| The weak property | 12 months | **1.8%**, with select room → checkout at just **9.33%** |
| Sister property | 22–31 Aug 2026 | 5.27% |
| Sister property | | 5.54% |
| Sister property | | 3.5% |

**Cause:** too many pricing options after room selection, which confused guests. At my manager's suggestion, the 1.58% headline conversion was de-emphasised and the report led with the largest drop-off and what to do about it.

---

## 5. Platform-wide numbers

| What | Figures |
|---|---|
| **Whole platform, 6 months (unique users)** | **7,577,209 opens → 2,079,714 room selections → 122,418 purchases (~1.6%)** |
| Exclusive Rates pop-up, platform (30 days) | 17.68K opens → 6,933 calendar → 258 pop-ups shown → 62 checkouts (0.35%) |
| Exclusive Rates pop-up, one hotel | 301 pop-ups → **134 emails given (44.5%)** → 16 purchases |
| Restaurant add-on | ~4.5% of bookings take one (9.1% at the best hotel); booking value **+18%** at one hotel and **−30%** at another |

The pattern across every board: the biggest drop is date or room selection → checkout, and checkout → purchase usually runs at 50–83%, except where a third party takes over mid-checkout (8–23%).

---

## 6. Smaller analyses

- **US resort fees** came to about **8.8–17.7% of the room price**.
- **SynXis mobile rate-plan usage** (no headline figure recorded).
- **Live-hotel detection**, using a threshold of fewer than 15 bookings.
- **Payment-resale estimate:** 70% of volume is in the EU, where the saving is small (1.5% → 1.4%); for the rest of the world it's 3.25% → 2.5%.

Mixpanel figures read from rolling windows were taken in November 2026 and will drift.

**Skills:** Mixpanel · BigQuery · funnel analysis · peer benchmarking · client reporting · experiment design
