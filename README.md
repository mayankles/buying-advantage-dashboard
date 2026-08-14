# The Buying Advantage

An interactive, single-file dashboard for exploring whether buying a home would leave you richer than renting the same home and investing the difference — across positive, neutral, and negative economic scenarios over a 30-year outlook.

[**Live demo**](https://mayankles.github.io/buying-advantage-dashboard/).

## What it does

You enter your purchase details — home price, down payment (as % or $), mortgage rate, loan term, and a comparable rent — plus optional assumptions like property tax, insurance, maintenance, and transaction costs. The dashboard then simulates three economies side by side:

- **Positive** — rates ease, the market stays hot (strong appreciation, cheap refinance, strong investment returns)
- **Neutral** — roughly today's conditions persist
- **Negative** — prices correct, rates get cut in a downturn

Every scenario parameter is editable. The defaults are linked the way rates, home prices, and markets have historically tended to move together, but nothing stops you from testing any combination.

The centerpiece is the **buying advantage** chart: for each year, the net worth you'd have from buying (home equity after selling costs, plus any invested cash-flow savings) minus the net worth from renting and investing your down payment, closing costs, and monthly savings instead. Where a line crosses zero is the break-even point — marked directly on the chart and on each scenario card. Click any year to pin the detailed ledger to that point in time.

## The model, briefly

- Standard mortgage amortization, computed monthly.
- If a scenario's available refinance rate (your rate plus that scenario's offset) is sufficiently below your locked rate, the model refinances at the start of year 2 and invests the payment savings.
- The renter's portfolio starts with the buyer's down payment and closing costs, and each month receives (or pays out) the difference between total ownership cost and rent, compounding at the scenario's investment return.
- "Net equity if sold" subtracts the remaining loan balance and selling costs from the home's value — so buying starts roughly 10% underwater, reflecting real round-trip transaction costs.
- Home appreciation, rent growth, and investment returns compound monthly from their annual rates.

## Running it

No build, no dependencies to install — it's one HTML file. Open `index.html` in a browser (Chart.js and fonts load from CDNs, so you'll want an internet connection).

## Disclaimer

This is a thinking tool, not financial advice. It simplifies aggressively: no PMI, no tax deductions, no capital gains treatment, constant scenario rates rather than paths, and a refinance rule of thumb. Talk to a financial advisor before making real decisions.

## Credits

Built collaboratively by [Mayank Tandon](https://github.com/mtandon09) and **Claude Fable 5** (in [Cowork mode](https://claude.com/claude) of the Claude desktop app), Anthropic's frontier model at the time. Claude designed the financial model, wrote the code, and iterated on the visual design — from an early light-mode prototype, through a dark fintech phase, to the current warm, editorial "data art" look — guided by Mayank's direction and feedback at every step. The scenario defaults were seeded from real market data (median US home price and average 30-year mortgage rates, August 2026).

## License

MIT — see [LICENSE](LICENSE).
