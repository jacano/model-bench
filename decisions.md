# Decisions

Dated on purpose: each row is what was decided with the numbers of that day, not a rule that
follows from the code. The live numbers are in `data/plans.json`, `data/tbench.json` and
`models.csv`; `plan`, `chart` and `measure` print them.

| Date | Decided | Why |
| --- | --- | --- |
| 2026-11-16 | OpenDesign Go is the subscription to pay for | $10 buys one pool of $220 of credits a month, and both admitted rows clear every gate. `plan` prints their rates. |
| 2026-11-16 | A subscription is a ceiling, not a meter | The fee is paid whether or not the plan is used, and the ceiling stops the damage. Fee ÷ what the plan lets a model spend, times the list rate and the multiplier, is the price `plan` prints. |
| 2026-11-16 | Command Code is worth it only for its ceiling | It loses on price on the models it shares with OpenDesign, but sells Opus 5.5 and Fable 5.2 at Terminal-Bench 65,8, where Go tops out at 40,0. Unverified, not rejected: it lapsed before any of its rows were measured. |
| 2026-11-17 | OpenGateway is out | Its $5 ran out. Its prices stay in `data/plans.json`, so `plan` still quotes it; bringing it back means its block in `dsh-config` and its id in `admitted:` here. |
| 2026-11-18 | OpenCode Go enters the table at $10 | Its ceiling is one allowance per model rather than a pool: at GLM-5.3's $500 through 2026-11-22, the fee over that ceiling prices a million input tokens at 0,028, the cheapest route above Haiku 5.5 on the board. |
| 2026-11-18 | The board moved and the menu did not | Copilot Fusion leads at 71,2, GPT-6.2 and Gemini 4 Carbon arrive, and Hy4 lands at 37,9, just under the 38,0 floor. No admitted route lost a gate, so `admitted:` is unchanged. |
| 2026-11-18 | MiMo V2.6 is four times dearer on OpenDesign | The page's multiplier table now says 4x where this file said 1x. Neither row is admitted, so the menu does not move. |
| 2026-11-18 | Command Code's other tiers are recorded, not priced | Go $1, Max $100, Provider $15 and Teams $40 now sit beside GOAT; every one of them moves the fee and the credits together or worse, so `plan` keeps GOAT. |
| 2026-11-18 | The console catalogue confirms the OpenDesign block and fills two OpenCode holes | All fourteen base rates match it. It prices Qwen4 Max and Hy4, which OpenCode's endpoint does not serve. Where it prints no cached-write rate, both blocks charge input: a write is billed as input, not free. |
| 2026-11-18 | The axis stays the input rate | A turn's shape belongs to the sessions, not to the provider, and providers without usage records cannot be compared on one. `--mix` prices a shape you name. |
| 2026-11-18 | The usage records are a check, not a metric | `verify` recomputes fifty calls the console recorded from their unit prices, and the block lands inside their 4-decimal rounding: the price is the billed one. They do not price the chart. |
| 2026-11-18 | deepseek-v4.1-flash-eco stays out | Measured on the Responses shape it is actually served on, it clears every gate but speed: 61 t/s against the 85 floor, with latency 2,28 s, cache 100% and tools 100%. The chat row's 59 was the model, not the route. `measure --api responses` now exists for the next time. |
| 2026-11-18 | The chart compares on two price shapes | `--by blended` prices the 97/2,5/0,5 convention and `--by yours` the measured shape, and the page switches between them. The blended column is the number Real API Pricing publishes, so the two can be read side by side. |
| 2026-11-18 | The chat shape is out | 70/30 with no cache is not a shape these subscriptions are used in: it priced a workload nobody has. `--mix` still prices it in one command if one is ever needed. |
| 2026-11-18 | The default axis is the blended million | A million input tokens is not what a subscription is spent on: the recorded calls are 99,2% cache. The page opens on `blended` and offers `yours` (the measured shape); `--by` picks one for the PNG. |
| 2026-11-18 | Command Code's block prices the plan's own table | The page lists 65 models with their monthly credits. The block named only some, let the rest fall back to the whole $100 pool, and priced fourteen models the plan does not sell — five times too cheap. The table is now the model list, and MiniMax M3 carries the -50% its name promised. |
| 2026-11-18 | Cache write leaves the table and the tooltip | No price here uses it: the blended million is cache read, fresh and output. The field stays in the data, where `verify` checks it against the billed unit prices. |
| 2026-11-18 | The yours toggle is out | The measured shape stays in `data/usage.json` and in `verify`'s report; a chart of one person's sessions is not a comparison across plans. `--mix` prices it when it is wanted. |
