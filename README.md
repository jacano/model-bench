# model-bench

What a DeepSeek Harness subscription actually costs, and what it can do: the price of a
million tokens after the plan's fee, its multiplier and its ceiling, Terminal-Bench as
capability, and the frontier through whatever nothing beats. The picture it publishes:
**https://jacano.github.io/model-bench/**

| Repository | Holds |
| --- | --- |
| **model-bench** (here) | The benchmark that chooses the model menu, and the page it publishes. |
| [dsh-config](https://github.com/jacano/dsh-config) | The DeepSeek Harness configuration: providers and the model menu. |
| [agent-skills](https://github.com/jacano/agent-skills) | Procedures an agent follows, with the code they need. |

## Run

```bash
python bench.py plan      # what a million tokens costs, per model, per plan
python bench.py chart     # price against the board, and the frontier through it
python bench.py chart --mix 25000,970000,5000   # another shape of a million tokens
python bench.py verify    # the console's recorded calls against the plan's price
python bench.py measure   # the stored rows against the gates, and the menu
python bench.py agentic --provider opendesign --model deepseek-v4.1-flash
```

The chart's axis is a million tokens at the blended shape: 97% cache, 2.5% fresh, 0.5% out,
the convention Real API Pricing publishes, so the two can be read side by side. `--mix
fresh,cache,out` prices another shape. `verify` is the other kind of evidence: it recomputes
fifty calls the console recorded, from their unit prices, and checks that the block's price
is the price that was billed. `measure --api responses` sends a route down the Responses
shape, which is the one OpenDesign serves, instead of chat completions.

`agentic` runs a real task through that route, three rounds, and pytest decides. `measure`
with `--model` and `--tbench` measures one route instead of checking the stored table.

Python 3. `plan` needs nothing else; `chart` draws the png with Pillow (`pip install
pillow`); `chart --html` writes the page without it; `agentic` runs DSH headless, so it needs
DSH installed and a key in its store. `measure` reads the DSH menu from another repository —
clone `dsh-config` beside this one, or point `DSH_CONFIG` at its `dsh/cordis.patch.yml`:

```bash
git clone https://github.com/jacano/dsh-config ../dsh-config
```

## Files

| | |
| --- | --- |
| `data/plans.json` | the plans, their windows, and the catalogue they price from |
| `data/tbench.json` | the board: what each model does on Terminal-Bench, and with which agent |
| `data/usage.json` | calls the console recorded, anonymised: what `verify` recomputes |
| `models.csv` | what each route measured on the wire |
| `models-policy.yml` | the gates, and which ids are admitted |
| `decisions.md` | what was decided, dated |
| `page.html` | the page `chart --html` fills in; Pages serves it from `docs/` |

## Adding a provider

1. **The numbers:** the fee, what it buys, the windows it resets on, the multiplier per
   model, and the rate per million for input, cache read, cache write and output. The two
   pages they come from go under `sources`.
2. **The block** in `data/plans.json`, then `plan` and `chart`. Both are free and say
   whether the route is worth measuring at all.
3. **Measure what survived:** `measure --model <id> --tbench <score>` prints a line in
   `models.csv`'s own shape. Paste it, add the id to `admitted:`, add the model to the menu
   in `dsh-config`, and `measure` must then exit 0.

A provider that stops before step 3 is unmeasured, not rejected: the chart shows it as a
point with no gate behind it.

## Where the numbers come from

Prices from the provider's own card and credits pages, named under `sources` in
`data/plans.json`: the card gives the fee, the credits page gives how far it goes. Capability
from Terminal-Bench, executed and graded. Behaviour measured by `measure` against the live
route, in `models.csv`. The price is checked against what was billed, in `data/usage.json`:
`verify` recomputes every recorded call from its unit prices. The provider never grades
itself, and only `measure` and `agentic` touch the network.

## License

MIT — see [LICENSE](LICENSE).
