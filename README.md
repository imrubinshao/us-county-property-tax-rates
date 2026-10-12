# U.S. county property tax rates

Property tax rates and median tax bills for every U.S. county, plus the official local tax rates
for Texas, North Carolina and Florida, as plain CSV files.

| File | Rows | What it contains |
|---|---|---|
| `data/counties.csv` | 3,133 | Median real estate tax, median home value, median effective rate, median owner household income and tax share of income for each county (and county equivalent) |
| `data/states.csv` | 51 | The same measures for the 50 states and D.C. |
| `data/texas_tax_rates_2025.csv` | 4,849 | Every Texas county, city, school district and special district rate for 2025, with the 2024 rate where the unit existed |
| `data/north_carolina_tax_rates_2025_26.csv` | 690 | County and municipal rates for 2025–26, combined and effective combined rates, previous-year rate and last reappraisal year |
| `data/florida_millage_2025.csv` | 67 | 2025 millage by county: county government, school board, special districts, total millage, taxes levied and change from 2024 |

## Definitions

- **Effective rate** = median real estate taxes paid ÷ median value of owner-occupied homes, in percent.
  It reflects what homeowners actually pay after typical exemptions and assessment practices, so it
  is comparable between states.
- **Tax share of income** = median real estate taxes ÷ median household income of owner households.
- **Rates per $100** (Texas, North Carolina) are dollars of tax per $100 of taxable value; **mills**
  (Florida) are dollars per $1,000.
- Ranks: 1 = highest effective rate.
- `unit_type` in the Texas file is derived from the taxing unit's name and ID: county, school, city,
  special (utility, water, improvement districts), emergency, hospital, college, other.

## Sources

- U.S. Census Bureau, American Community Survey 2019–2023 5-year estimates, tables B25103 (median
  real estate taxes paid), B25077 (median home value), B25003 (tenure), B25119 (household income by
  tenure) and B01003 (population)
- Texas Comptroller of Public Accounts, tax rates and levies, 2025 and 2024
- North Carolina Department of Revenue, county and municipal tax rates and effective tax rates,
  2025–2026 and 2024–2025
- Florida Department of Revenue, Ad Valorem Valuation and Tax Data Book, millage and taxes levied
  2025 (data extract November 2025)

ACS figures are survey estimates; small counties carry wide margins of error, and a few counties
without enough responses are omitted. Connecticut appears as its nine planning regions, the Census
county equivalents since 2022.

## Updates

The files are refreshed when the sources publish new data: the ACS each December, Texas rates in
spring, North Carolina in summer and Florida's final data book in January.

## License and citation

The compiled dataset is released under CC BY 4.0 (see LICENSE). The underlying government data is
public. Please cite as:

> County Property Taxes, *U.S. county property tax rates* (2026), https://countypropertytaxes.com/
