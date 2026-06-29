# Climate Value-at-Risk (CVaR) Screening Tool

Built by [The Sustainable Analyst](https://thesustainableanalyst.substack.com) —
a research project applying quantitative financial tools to climate transition risk.

A financial stress test tool simulating the impact of carbon price scenarios on
companies' valuation and operational performance. **Sector-agnostic**, applicable
to any listed company with available GHG emissions data.

## What it does

- Computes five CVaR indicators per company: CVaR Market Cap and CVaR EBITDA (each produced twice — without and with SBTi transition plan), plus a Delta CVaR isolating the financial value of the decarbonization commitment
- Applies NGFS carbon price trajectories interpolated annually over the full horizon (2025–2035)
- Runs automatically across all three NGFS scenarios and two horizons (2030 and 2035) in a single execution — 6 scenario/horizon combinations
- Models company-specific WACC from static Excel inputs (Beta, total debt, market cap, interest expense)
- Integrates SBTi Scope 3 decarbonization plans as a progressive linear reduction toward `SBTi_Target_Year`
- Tracks SBTi execution progress per company: reduction achieved vs. target, observed vs. required annual rate, acceleration factor, and years remaining
- Outputs carbon intensity (tCO2e/M€ revenue) and debt/EBITDA ratio as complementary risk indicators
- Produces a year-by-year cash flow detail table (Table 4) covering 2025→2035 across all scenarios, for both NoPlan and WithPlan runs
- Ranks companies by climate transition risk exposure within a peer group

## Methodology

Full methodology available in the white paper:
https://thesustainableanalyst.substack.com/p/climate-cvar-methodology-of-a-financial

## Version history

| Version | Changes |
|---|---|
| V1 | Initial release — sector-level WACC, single target carbon price applied from year one, no SBTi integration |
| V2 | Company-specific WACC — Static Excel input replacing Yahoo Finance API — Annual NGFS carbon price trajectory (linearly interpolated) — Progressive linear Scope 3 decarbonization toward `SBTi_Target_Year` |
| V3 | SBTi execution tracking module (progress %, observed vs. required rate, acceleration factor) — Automated multi-scenario/multi-horizon loop (3 scenarios × 2 horizons in one run) — Table 4: year-by-year cash flow detail (2025→2035, all scenarios, NoPlan and WithPlan) — New required Excel input: `SBTi_Baseline_Year` — WACC parameters updated to Damodaran May 2026 |

## Data sources

- GHG emissions: company sustainability reports & CDP
- Carbon price trajectories: NGFS Phase V, GCAM 6.0
- WACC inputs: company-specific calculations (Beta, risk-free rate, ERP — Damodaran May 2026)
- Financial data: manually entered in static Excel file (sourced from official financial reports)

## How to use

1. Download `CVaR_Tool_Template.xlsx` from the root of this repository
2. Fill in your data across the three sheets:

   **`Companies` sheet** — one row per company (financial data in millions, native currency):
   `Name`, `Ticker`, `Currency`, `Market_Cap`, `Total_Debt`, `Beta`, `Interest_Expense`, `EBITDA`, `Total_Revenue`, `Scope_1_2`, `Scope_3`, `%_of_Green_Revenue`, `Pass_Through`, `Scope_3_SBTi_Current`, `Scope_3_SBTi_Baseline`, `Carbon_Reduction_Plan_Scope_3`, `SBTi_Baseline_Year`, `SBTi_Target_Year`

   **`Currencies` sheet** — one row per currency used, EUR/local conversion rates

   **`Carbon_Prices` sheet** — NGFS anchor points for 2025, 2030, 2035 across three scenarios: `Current_Policies`, `Delayed_Transition`, `Net_Zero_2050`

3. Open `V3_EN_Climate_Stress_Test.ipynb` in Google Colab
4. Update the Excel file path at the top of the first cell to point to your file on Google Drive
5. Run all cells — the tool automatically iterates across all three scenarios and both horizons (2030 and 2035)

## Example analyses

**European Luxury Sector** — LVMH, Hermès, Kering, Richemont, Burberry, Moncler (using the V1 of the tool)
- [English version](https://thesustainableanalyst.substack.com/p/the-european-luxury-sector-facing?r=a7sex)
- [French version](https://thesustainableanalyst.substack.com/p/le-secteur-du-luxe-europeen-face?r=a7sex)

**Global Sportswear Sector** — Nike, Adidas, Puma, Lululemon, On Running, Under Armour (Using the V3 of the tool) - 
- [English version](https://thesustainableanalyst.substack.com/p/the-sportswear-sector?r=a7sex)

**Pharmaceutical Sector** - Novonordisk, Roche, Astrazeneca, Sanofi, Merck, GSK, Eli Lilly
- [English version](https://thesustainableanalyst.substack.com/p/the-pharmaceutical-sector?r=a7sex)

## Disclaimer

All data were taken from public sources only.
This tool is built for screening purposes only. It does not constitute financial advice.
