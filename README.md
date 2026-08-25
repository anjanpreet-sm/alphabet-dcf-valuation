# Alphabet Inc. — DCF Valuation Model

A bottom-up, segment-level discounted cash flow model for Alphabet Inc. built from these sources: the FY2022–FY2025 10-K filings and the Q4 2025 earnings call transcript.

**Implied share price: $200.74** vs. **actual price: $313.80** (as of Dec 31, 2025)
The model implies Alphabet is trading 36% above its DCF-derived fair value. See below for the full explanation of why this is a genuine, sourced finding and not an error to be tuned away.

---

## Approach

Built bottom-up in four stages:

1. **Historical statements (2022–2025)**: Income Statement, Cash Flow Statement and a simplified Balance Sheet (Cash, Marketable Securities, Debt only), reconstructed and verified directly against Alphabet's 10-K filings.
2. **Historical analysis**: margin trends, segment growth rates and CapEx/FCF dynamics which are all used to identify what's actually driving the business.
3. **Forecast (2026–2030)**: six of their revenue segments modeled independently with each following its own growth logic; followed by opex, D&A, CapEx, and working capital.
4. **DCF**: FCFF discounted at WACC, with a normalized terminal value, bridged to equity value and implied share price.

---

## Historical financials

| | 2022A | 2023A | 2024A | 2025A |
|---|---|---|---|---|
| Revenue | $282.8bn | $307.4bn | $350.0bn | $402.8bn |
| Operating Margin | 26.5% | 27.4% | 32.1% | 32.0% |
| Free Cash Flow | $60.0bn | $69.5bn | $72.8bn | $73.3bn |
| CapEx / Revenue | 11.1% | 10.5% | 15.0% | 22.7% |

**The core historical tension:** margins expanded every year, but FCF margin compressed (21.2%→18.2%) because CapEx more than doubled as a share of revenue — the AI infrastructure buildout eating into cash conversion even as the underlying business got more profitable. This tension we see is the central theme for the the entire forecast.

---

## Revenue forecast — segment by segment

Modeled as six independent lines rather than one blended growth rate, each reasoned from historical trend + Q4 2025 management commentary:

| Segment | 2025A | 2030E | Method / logic |
|---|---|---|---|
| Google Search & other | $224.5bn | $384.6bn | Tapered 13.4%→8.7%. AI Mode/Overviews cited as accelerant; tapered per "law of large numbers" on an already-massive base |
| YouTube ads | $40.4bn | $60bn | Constant ~$4bn/yr dollar-add (not %), reflecting a maturing segment with no distinct new catalyst |
| Google Network | $29.8bn | $29.3bn | Decline decelerating toward flat; zero management commentary suggests low strategic priority |
| Subscriptions/Platforms/Devices | $48.0bn | $105.3bn | Tapered 19%→15%; AI-plan upsell (Gemini in Google One) + AI-driven storage demand |
| Google Cloud | $58.7bn | $287.4bn | Rise-then-taper (38%→39%→35%); it's explicitly **supply-constrained** not demand-constrained so with its $240bn backlog, capacity is catching up over time |
| Other Bets / Hedging | ~$1.5bn / ~$0 | flat | Immaterial, no forecastable driver |

**Result:** Total revenue reaches **$868.0bn by 2030** (16-17% annual growth), above the 2025 historical rate (15.1%) which is a deliberate, sourced consequence of Cloud's rising share of the mix, not blanket acceleration across the business.

---

## Operating & cash flow forecast

- **Cost of Revenue:** improving trend (45%→40% of revenue, 2022–2025) assumed to reverse and climb back to 40.5% by 2030, reflecting the lagged P&L impact of the CapEx surge on depreciation (per management's explicit 2026 depreciation-acceleration guidance)
- **R&D:** climbs to 15.5% of revenue (continued investment in AI talent)
- **CapEx:** anchored to management's stated **$175–185bn 2026 guidance**, then a decelerating growth (20%→10%→5%→2%) through 2030 due to supply constraints— revised down from an initial draft that produced an mathematically absurd >$1 trillion CapEx figure by 2030
- **D&A:** modeled with an explicit lag to the CapEx cycle, accelerating in 2026 per management guidance before moderating
- **Working Capital:** no directional trend historically so held flat at a small % of revenue rather than forcing a fake trend onto the noise

---

## WACC

| Input | Value | Source |
|---|---|---|
| Risk-free rate | 4.163% | 10-Year U.S. Treasury, Dec 31, 2025 (CNBC) |
| Beta | 1.24 | 5-year beta (Investing.com) |
| Equity Risk Premium | 4.23% | Damodaran implied ERP, Jan 1, 2026 |
| **Cost of Equity (CAPM)** | **9.41%** | |
| Pre-tax Cost of Debt | 4.66% | Alphabet's Aa2/AA+ credit rating + typical spread over risk-free |
| After-tax Cost of Debt | 3.91% | Adjusted for 16% tax rate |
| Capital structure | 98.75% equity / 1.25% debt | Market cap ($3.84tn) vs. total debt ($48.5bn) |
| **WACC** | **9.34%** | |

Alphabet's capital structure is so overwhelmingly equity-funded that WACC is almost entirely driven by Cost of Equity; debt barely moves the overall blended rate despite its much lower cost.

---

## DCF output

| | Value |
|---|---|
| PV of FCFF (2026–2030) | $58.0bn |
| PV of Normalized Terminal Value | $2,318.4bn |
| **Enterprise Value** | **$2,376.4bn** |
| + Cash & Investments (2025) | $126.8bn |
| − Total Debt (2025) | $48.5bn |
| **Equity Value** | **$2,454.7bn** |
| ÷ Diluted Shares Outstanding | 12.228bn |
| **Implied Share Price** | **$200.74** |
| Actual Share Price (12/31/25) | $313.80 |
| **Implied vs. Actual** | **−36%** |

The 2026–2030 forecast contributes only **~2.4% of total Enterprise Value** — 97.6% comes from the Terminal Value. This means the valuation is far more sensitive to WACC and the terminal growth rate than to any single operating assumption (including CapEx, which cancels out entirely in the normalized terminal year).

---

## Why the gap exists

A DCF that lands 36% below the market price for this is not treated has an error to be tuned away such as by reverse-engineering assumptions to match a target price which defeats the purpose of the exercise. Instead, the gap was investigated directly:

- **Sensitivity testing:** raising the terminal growth rate from 2.5% → 3.5% moves the implied price from $200.74 → ~$233 which closed roughly a third of the gap, but not all of it.
- **Solving backward:** fully closing the gap to $313.80 would require g ≈ 5%, more than double the base case and approaching WACC itself — a rate this model treats as too aggressive to defend against standard GDP-growth benchmarks (CBO long-run real GDP ~1.8%).
- **Most likely explanation:** the market may be pricing in a belief that AI expands Alphabet's *total addressable market* rather than simply reallocating share within it — an assumption this model deliberately does not adopt without stronger evidence, in favor of a more conservative, GDP-anchored terminal assumption.

The base case (g = 2.5%, WACC = 9.34%) is therefore kept with this sensitivity analysis presented as supporting context rather than a "correction."

---

## Key lessons from this project

- Every forecast assumption is tied to a specific, sourced piece of evidence (10-K MD&A + earnings call transcript) rather than an assumed percentage.
- The shape of a growth curve must match the story behind it and several early drafts (Search, Subscriptions, Cloud) were rejected and rebuilt after failing this test.
- Different revenue segments can face fundamentally different constraints (demand-side/saturation vs. supply-side/capacity) and this directly shapes whether growth tapers immediately or rises before tapering.
- Always sanity-check dollar outputs, not just growth rates — an early CapEx draft implied >$1 trillion of annual spend by 2030 which was then revised.
- Always sanity-check the aggregate, not just individual components — an early Cloud assumption caused Total Revenue growth to accelerate every year through 2030, an unrealistic outcome for a company this size, caught via a overall company-level revenue check rather than a segment-level one.
- A large gap between model output and market price is a finding to investigate and explain, not just a bug to eliminate by reverse-engineering the discount rate or growth assumption.

---
*All figures sourced from Alphabet's SEC filings (10-K, FY2022–FY2025) and the Q4 2025 earnings call transcript*
