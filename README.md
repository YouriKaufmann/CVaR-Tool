# Climate Value-at-Risk (CVaR) Screening Tool

A financial stress test tool simulating the impact of carbon price scenarios on companies' valuation and operational performance. **Sector-agnostic** — applicable to any listed company with available GHG emissions data.

## What it does
- Computes two CVaR scores per company: Market Cap impact (%) and EBITDA impact (%)
- Applies user-defined carbon price scenarios (e.g. NGFS Phase V trajectories)
- Outputs carbon intensity, debt/EBITDA ratio, and annualized cost impact
- Ranks companies by climate transition risk exposure within a peer group

## Methodology
Full methodology available in the white paper 
  English version → https://thesustainableanalyst.substack.com/p/climate-cvar-methodology-of-a-financial?r=a7sex
  French version → https://thesustainableanalyst.substack.com/p/cvar-climatique-methodologie-dun?r=a7sex

## Data sources
- GHG emissions: company sustainability reports & CDP
- Carbon price trajectories: NGFS Phase V, GCAM 6.0
- WACC: Damodaran sector data
- Financial data: Yahoo Finance API

## How to use
1. Open the notebook in Google Colab
2. Fill in your company data in the Excel input file (ticker, emissions, pass-through, WACC, green revenue %)
3. Set carbon price parameters and time horizon
4. Run all cells

## Example analysis
Applied to the European luxury sector (LVMH, Hermès, Kering, Richemont, Burberry, Moncler) 
  English version → https://thesustainableanalyst.substack.com/p/the-european-luxury-sector-facing?r=a7sex
  French version → https://thesustainableanalyst.substack.com/p/le-secteur-du-luxe-europeen-face?r=a7sex

## Note
One version is in english and one is in french.

## Disclaimer
All the data were taken from public sources only.
This tool is built for screening purposes only. It does not constitute financial advice.

