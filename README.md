# Climate Value-at-Risk (CVaR) Screening Tool

Built by [The Sustainable Analyst](https://thesustainableanalyst.substack.com) — 
a research project applying quantitative financial tools to climate transition risk.

A financial stress test tool simulating the impact of carbon price scenarios on 
companies' valuation and operational performance. **Sector-agnostic**, applicable 
to any listed company with available GHG emissions data.

## What it does

- Computes two CVaR scores per company: Market Cap impact (%) and EBITDA impact (%)
- Applies user-defined carbon price scenarios (e.g. NGFS Phase V trajectories)
- Models company-specific WACC (rather than sector averages)
- Integrates SBTi decarbonization plans (Scope 3 only) to quantify their financial value
- Outputs carbon intensity, debt/EBITDA ratio, and annualized cost impact
- Ranks companies by climate transition risk exposure within a peer group

## Methodology

Full methodology available in the white paper:
- https://thesustainableanalyst.substack.com/p/climate-cvar-methodology-of-a-financial?r=a7sex

## Version history

| Version | Change |

| V1 | Initial release — sector-level WACC, no SBTi integration |
| V2 | Company-specific WACC + SBTi Scope 3 plan integration |

## Data sources

- GHG emissions: company sustainability reports & CDP
- Carbon price trajectories: NGFS Phase V, GCAM 6.0
- WACC: WACC: company-specific calculations (Beta, risk-free rate, ERP — Damodaran May 2026)
- Financial data: Yahoo Finance API

## How to use

1. Open the notebook in Google Colab
2. Fill in your company data in the Excel input file 
   (Name, Ticker, Scope_1_2, Scope_3, %_of_Green_Revenue, Pass_Through, 
    Scope_3_SBTi_Current, Scope_3_SBTi_Baseline, Carbon_Reduction_Plan_Scope_3)
3. Set carbon price parameters and time horizon
4. Run all cells

## Example analyses

**European Luxury Sector** — LVMH, Hermès, Kering, Richemont, Burberry, Moncler (V1)
- [English version](https://thesustainableanalyst.substack.com/p/the-european-luxury-sector-facing?r=a7sex)
- [French version](https://thesustainableanalyst.substack.com/p/le-secteur-du-luxe-europeen-face?r=a7sex)

**Global Sportswear Sector** — Nike, Adidas, Puma, Lululemon, On Running, Under Armour (V2)
- [English version](https://thesustainableanalyst.substack.com/p/INSERT_LINK)

## Disclaimer

All data were taken from public sources only.  
This tool is built for screening purposes only. It does not constitute financial advice.
