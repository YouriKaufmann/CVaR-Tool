# Climate Value-at-Risk (CVaR) Screening Tool

Built by [The Sustainable Analyst](https://thesustainableanalyst.substack.com) —
a research project applying quantitative financial tools to climate transition risk.

A financial stress test tool simulating the impact of carbon price scenarios on
companies' valuation and operational performance. **Sector-agnostic**, applicable
to any listed company with available GHG emissions data.

## What it does

- Computes five CVaR indicators per company: CVaR Market Cap and CVaR EBITDA (each produced twice — without and with SBTi transition plan), plus a Delta CVaR isolating the financial value of the decarbonization commitment
- Applies NGFS carbon price trajectories interpolated annually over the full horizon (2025–2035)
- Models company-specific WACC from static Excel inputs (Beta, total debt, market cap, interest expense)
- Integrates SBTi Scope 3 decarbonization plans as a progressive linear reduction toward `SBTi_Target_Year`
- Outputs carbon intensity (tCO2e/M€ revenue) and debt/EBITDA ratio as complementary risk indicators
- Ranks companies by climate transition risk exposure within a peer group

## Methodology

Full methodology available in the white paper:
https://thesustainableanalyst.substack.com/p/climate-cvar-methodology-of-a-financial

## Version history

| Version | Changes |
|---|---|
| V1 | Initial release — sector-level WACC, single target carbon price applied from year one, no SBTi integration |
| V2 | Company-specific WACC — Static Excel input replacing Yahoo Finance API — Annual NGFS carbon price trajectory (linearly interpolated) — Progressive linear Scope 3 decarbonization toward `SBTi_Target_Year` |

## Data sources

- GHG emissions: company sustainability reports & CDP
- Carbon price trajectories: NGFS Phase V, GCAM 6.0
- WACC inputs: company-specific calculations (Beta, risk-free rate, ERP — Damodaran May 2026)
- Financial data: manually entered in static Excel file (sourced from official financial reports)

## How to use

1. Open the notebook in Google Colab
2. Fill in your company data in the Excel input file (`Companies` sheet):
   - Non-financial: `Name`, `Ticker`, `Currency`, `Scope_1_2`, `Scope_3`, `%_of_Green_Revenue`, `Pass_Through`, `Scope_3_SBTi_Current`, `Scope_3_SBTi_Baseline`, `Carbon_Reduction_Plan_Scope_3`, `SBTi_Target_Year`
   - Financial (in millions, native currency): `Market_Cap`, `Total_Debt`, `Beta`, `Interest_Expense`, `EBITDA`, `Total_Revenue`
3. Fill in FX rates in the `Currencies` sheet
4. Fill in NGFS carbon price anchor points (2025, 2030, 2035) in the `Carbon_Prices` sheet
5. Set `ACTIVE_SCENARIO` and run all cells

## Example analyses

**European Luxury Sector** — LVMH, Hermès, Kering, Richemont, Burberry, Moncler (V1)
- [English version](https://thesustainableanalyst.substack.com/p/the-european-luxury-sector-facing?r=a7sex)
- [French version](https://thesustainableanalyst.substack.com/p/le-secteur-du-luxe-europeen-face?r=a7sex)

**Global Sportswear Sector** — Nike, Adidas, Puma, Lululemon, On Running, Under Armour (V2) - coming soon

## Disclaimer

All data were taken from public sources only.
This tool is built for screening purposes only. It does not constitute financial advice.
