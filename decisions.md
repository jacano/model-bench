# Decisions

Dated on purpose: each row is what was decided with the numbers of that day, not a rule that
follows from the code. The live numbers are in `data/plans.json`, `data/tbench.json` and
`models.csv`; `plan`, `chart` and `measure` print them.

| Date | Decided | Why |
| --- | --- | --- |
| 2026-11-16 | OpenDesign Go is the subscription to pay for | $10 buys one pool of $220 of credits a month, and both admitted rows clear every gate. `plan` prints their rates. |
| 2026-11-16 | A subscription is a ceiling, not a meter | The fee is paid whether or not the plan is used, and the ceiling stops the damage. Fee ÷ what the plan lets a model spend, times the multiplier: that is the price `plan` prints. |
| 2026-11-16 | Command Code is worth it only for its ceiling | It loses on price on the models it shares with OpenDesign, but sells Opus 5.5 and Fable 5.2 at Terminal-Bench 65,8, where Go tops out at 40,0. Unverified, not rejected: it lapsed before any of its rows were measured. |
| 2026-11-17 | OpenGateway is out | Its $5 ran out. Its prices stay in `data/plans.json`, so `plan` still quotes it; topping it up is the whole of bringing it back. |
