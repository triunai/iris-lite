---
theme: credit
status: stable
confidence: medium
first_opened: 2026-07-26
last_reviewed: 2026-07-28
previous_status: dormant
status_change_reason: "First sourced credit-spread data via FRED (IG/HY OAS) - gap closed after 3 runs of insufficient data"
sensitive_assets: ["IG spreads", "HY spreads", "sovereign spreads"]
sensitive_sectors: ["banks", "highly-levered issuers"]
next_catalysts: ["any material spread-widening event", "next credit-market commentary from a Tier 1/2 source"]
invalidation_conditions: ["a confirmed widening in IG/HY spreads coinciding with the equity selloff (would upgrade this to an active risk-off theme)"]
---

# Credit

## Thesis

No credit-spread data has been sourced yet — explicitly logged as unavailable in the first brief. Given the equity/vol stress on 23 Jul (S&P -1.0%, VIX >19), whether credit confirms or diverges from that stress is an open and important question for the next run.

## Supporting Evidence

None logged yet.

## Contradicting Evidence

None logged yet.

## Sources

See briefs/2026/07/2026-07-24-morning-brief.md §4 (Cross-Asset Signal Matrix — Credit row: 'Unavailable from a sufficiently reliable source').

## Observation 2026-07-28

Gap closed: FRED publishes free, fetchable US IG OAS (BAMLC0A0CM) and HY OAS (BAMLH0A0HYM2) series. Latest available (24 Jul, reporting lag to this run): IG 0.80% (80bp), HY 2.79% (279bp) - both in a historically tight/calm range, showing NO credit-market stress through the entire oil/geopolitical shock episode (Brent >$100 to $88.36 and back), even as equity vol ticked up intraday Monday (VIX 17.7-19.4 range, unconfirmed close). This is itself a signal: credit investors read the shock as transitory/event-driven rather than a fundamental risk re-rating (Analyst inference). NOTE (2026-07-28 v2.1.0 correction): the OAS-vs-VIX comparison above mixes a Friday print against Monday's vol reading, not a same-day read - see the same-day HYG/LQD proxy fix (hyg-lqd-same-day pair, both closed up Monday, IG slightly outperforming HY) for the valid same-day credit signal. EM sovereign spread proxy (EMBI GD) only available quarter-end (235bp, 30 Jun) - no July update sourced; CDX IG/HY remain paywalled/unsourced. Status: dormant -> stable, confidence low -> medium. See trackers/liquidity-plumbing.csv (new tracker, OPERATING-INSTRUCTIONS.md §14) for the full plumbing read (TGA, SOFR/EFFR also now tracked - no funding stress visible).
