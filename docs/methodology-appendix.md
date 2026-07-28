# Methodology Appendix (Operator Reference)

Added 2026-07-28 (v2.1.0), in response to an external review noting that file paths,
tracker names, and "new standing section" labels belonged out of the reader-facing
brief/digest and into a separate reference. **This document is for whoever operates
or audits this desk — the daily brief and any digest should point here once, rather
than repeating this detail inline.**

---

## Where things live

| What | File |
|---|---|
| Operating rules (all of them) | `OPERATING-INSTRUCTIONS.md` |
| Instrument/ticker list | `config/instruments.yaml` |
| Relationship/ratio pair definitions | `config/ratio-pairs.yaml` |
| Commodity-country exposure map (with sensitivity/transmission/buffers) | `config/country-commodity-exposure.yaml` |
| Daily ratio levels/changes | `trackers/relationship-dashboard.csv` |
| Credit/funding plumbing readings | `trackers/liquidity-plumbing.csv` |
| Political reaction-function board entries | `trackers/political-reaction-function.csv` |
| Alternative-data sightings (sparse, tiered) | `trackers/altdata-pulse.csv` |
| Plain-English glossary | `docs/glossary.md` |
| This document | `docs/methodology-appendix.md` |
| Core trackers (releases, revisions, event calendar, positioning, geopolitical, trade-policy, digital-asset flows) | `trackers/*.csv` (see OPERATING-INSTRUCTIONS.md §8.1-8.2) |
| Theme files (25 as of v2.1.0) | `themes/*.md` |
| Regime and scenarios | `state/current-regime.json`, `scenarios/current-scenarios.yaml` |
| Daily briefs | `briefs/YYYY/MM/YYYY-MM-DD-morning-brief.md` |
| Monday weekly file | `weekly/YYYY-Www-week-ahead.md` |

## What's live vs. what's a genuine gap (as of 2026-07-28, v2.1.0)

**Live and real:** the relationship/ratio engine (23 defined pairs); the commodity-country exposure map (29 countries, each with a sensitivity/transmission/buffers read, not just a categorical label); the liquidity-plumbing tracker (FRED-sourced OAS/TGA/SOFR/EFFR, plus a same-day HYG/LQD proxy rule for when the lagged official series isn't enough); the political reaction-function board (nine-category fixed rubric, qualitative bands only, no fabricated scores); the expanded glossary; the Daily Global Country Snapshot roster (§7.9); the six-part divergence micro-template (§13.2).

**Structurally in place but not yet exercised on a real run:** the rotating regional deep-dive schedule (§7.7) — Latin America, Australia/NZ, Africa & wider Middle East now have a named weekly slot; no run has yet landed on their dedicated day.

**Genuine, ongoing gaps:** no live alternative-data feed exists (no satellite/AIS/credit-card-panel API access) — §16.1 documents which public proxies (TSA throughput, MBA mortgage applications, job-postings indices, Google Trends) are realistically checkable and which theme they belong to instead of the alt-data tracker; percentile/z-score/correlation statistics on the ratio dashboard need this desk's own logged history to build up (started 2026-07-28; meaningful 1-week diffs should appear within the week, 1-month diffs within the month); CDX levels remain paywalled; the 3-month/6-month regional strategic sector-rotation map remains unsourced (a recurring gap independent of the v2.0.0/v2.1.0 upgrades); a same-day JGB 2Y print was not sourced on 2026-07-28 (Friday's print was used as the latest available context) — a specific, named gap for the next run to try to close.

## Revision history relevant to this appendix

- **2026-07-28 (v2.0.0→ v2.1.0):** an external review of the first digest produced under v2.0.0 (scored 8.3/10) identified specific methodological weaknesses, each addressed in v2.1.0: (1) some ratios mixed venues/units across the days being compared (LME vs. COMEX copper) and still published a directional read — fixed via the §13.1 comparability-strictness rule, which now requires marking `not comparable` rather than a caveated-but-still-published number; (2) the USD/JPY divergence used the 10-year US-Japan yield gap as the "textbook carry driver," when the near-term carry trade is more directly tied to the 2-year/short-end differential and OIS-implied policy path — fixed in `config/ratio-pairs.yaml`; (3) a credit-vs-volatility comparison used a lagged Friday OAS print against Monday's equity-vol reading, which is not a same-day comparison — fixed via the §14 same-day HYG/LQD proxy rule; (4) country winners/losers were a binary categorical label with no sense of how much a given country's economy actually depends on the commodity in question — fixed via the `sensitivity`/`transmission`/`buffers` fields added to every entry in `config/country-commodity-exposure.yaml`; (5) the political reaction-function board risked becoming "intelligent-sounding storytelling" built from selectively-chosen evidence — fixed via the §17.1 nine-category fixed rubric, each scored independently; (6) divergence call-outs stated the puzzle without systematically working through what would confirm or invalidate it — fixed via the §13.2 six-part micro-template; (7) the reader-facing digest repeated file paths and implementation detail that belonged in a reference document, not the narrative — this document is that fix.
