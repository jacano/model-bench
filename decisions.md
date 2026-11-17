# Decisions

Dated on purpose: each row is what was decided with the numbers of that day, not a rule
that follows from the code. The live numbers are in `data/plans.json`, `data/tbench.json`
and `models.csv`; `plan`, `chart` and `measure` print them.

| Date | Decided | Why |
| --- | --- | --- |
| 2026-11-16 | OpenDesign Go is the subscription to pay for | $10 buys one pool of $220 of credits a month, and both admitted rows clear every gate: DeepSeek V4.1 Flash at 0,00682/0,00014/0,02727 per million, Claude Haiku 5.5 at 0,00909/0,00091/0,04545 (input/cache read/output). |
| 2026-11-16 | Command Code is worth it only for its ceiling | It loses on price on both models it shares with OpenDesign (V4.1 Flash input 0,01812 against 0,00682), but sells Opus 5.5 and Fable 5.2 at Terminal-Bench 65,8, where Go tops out at Haiku's 40,0. Unverified, not rejected: it lapsed with none of its rows measured. |
| 2026-11-16 | A subscription is a ceiling, not a meter | The fee is paid whether or not the plan is used, and the ceiling stops the damage. Rate = fee ÷ what the plan lets a model spend; × the multiplier = the price `plan` prints. That is why the price is not a gate. |
| 2026-11-16 | The 220 was one pool, not a sum of per-model caps | The console lists a monthly figure per model (15 Haiku, 120 DeepSeek, 220 eco) and reading them as caps priced Haiku fourteen times too high for an hour. The credits page says Go is one pool, and those figures are what a slice buys. |
| 2026-11-17 | The table quotes dollars per million, not turns | A turn is a shape of traffic (1k fresh, 89k cache read, 1,5k out) and it decided the ranking: two lanes four times apart on it, within ten per cent on an invoice. The table was quoting an assumption, not a price. |
| 2026-11-17 | OpenGateway is out | Its $5 ran out. A route that cannot be called is not one this repo recommends; its prices stay in `data/plans.json` so `plan` still quotes it, and topping it up is the whole of bringing it back. |
