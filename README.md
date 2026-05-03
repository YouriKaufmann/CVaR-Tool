# CVaR-Tool
Climate Value-at-Risk screening tool for carbon transition risk assessment.
Climate Value-at-Risk (CVaR) Screening Tool
A financial stress test tool simulating the impact of carbon price scenarios on companies' valuation and operational performance. Sector-agnostic, applicable to any listed company with available GHG emissions data.

What it does

Computes two CVaR scores per company : Market Cap impact (%) and EBITDA impact (%)
Applies user-defined carbon price scenarios (e.g. NGFS Phase V trajectories)
Outputs carbon intensity, debt/EBITDA ratio, and annualized cost impact
Ranks companies by climate transition risk exposure within a peer group

Methodology
Full methodology available in the white paper → XXX
Data sources

GHG emissions : company sustainability reports & CDP
Carbon price trajectories : NGFS Phase V, GCAM 6.0
WACC : Damodaran sector data
Financial data : Yahoo Finance API

How to use

Open the notebook in Google Colab
Fill in your company data in the Excel input file (ticker, emissions, pass-through, WACC, green revenue %)
Set carbon price parameters and time horizon
Run all cells

Example analysis
Applied to the European luxury sector (LVMH, Hermès, Kering, Richemont, Burberry, Moncler) → XXX
Note
Code comments are currently in French — English version coming soon.
Disclaimer
This tool is built for screening purposes only. It does not constitute financial advice.
Code comments are currently in French — English version coming soon.
Disclaimer
This tool is built for screening purposes only. It does not constitute financial advice.
