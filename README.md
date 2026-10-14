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

<!-- columns:start -->
## Columns

### `data/counties.csv`

| Column | Description |
| --- | --- |
| `fips` | The county's five-digit Federal Information Processing Standards code. |
| `state` | The county's two-letter state abbreviation. |
| `county` | The county name. |
| `median_real_estate_tax` | The median annual real estate tax in US dollars, from ACS 2019-2023 5-year estimates. |
| `median_tax_flag` | '10000+' when the median tax is $10,000 or more and '<200' when it is below $200 (the Census reports these as 10001 and 199, so the effective rate is a bound); empty otherwise. |
| `median_home_value` | The median owner-occupied home value in US dollars, from ACS 2019-2023 5-year estimates. |
| `effective_rate_pct` | Median real estate taxes divided by median home value, expressed as a percent. |
| `median_owner_household_income` | The median income of owner households in US dollars, from ACS 2019-2023 5-year estimates. |
| `tax_share_of_income_pct` | Median tax divided by median owner household income, expressed as a percent. |
| `owner_occupied_units` | The number of owner-occupied housing units. |
| `population` | The county population from ACS 2019-2023 5-year estimates. |
| `rank_in_state` | The county's effective rate rank within its state, with 1 meaning the highest rate. |
| `rank_national` | The county's effective rate rank nationally, with 1 meaning the highest rate. |

### `data/states.csv`

| Column | Description |
| --- | --- |
| `fips` | The state's two-digit Federal Information Processing Standards code. |
| `state` | The two-letter state abbreviation. |
| `name` | The state name. |
| `median_real_estate_tax` | The median annual real estate tax in US dollars, from ACS 2019-2023 5-year estimates. |
| `median_home_value` | The median owner-occupied home value in US dollars, from ACS 2019-2023 5-year estimates. |
| `effective_rate_pct` | Median real estate taxes divided by median home value, expressed as a percent. |
| `median_owner_household_income` | The median income of owner households in US dollars, from ACS 2019-2023 5-year estimates. |
| `rank` | The state's effective rate rank, with 1 meaning the highest rate. |
| `counties` | The number of counties represented in the state estimate. |

### `data/texas_tax_rates_2025.csv`

| Column | Description |
| --- | --- |
| `county_fips` | The county's five-digit Federal Information Processing Standards code. |
| `county` | The county name. |
| `taxing_unit` | The name of the taxing unit. |
| `unit_type` | The taxing unit type: county, school, city, special, emergency, hospital, college, or other. |
| `rate_per_100_2025` | The 2025 tax rate in dollars per $100 of taxable value (0 for units that set no rate, such as inactive utility districts). |
| `rate_per_100_2024` | The 2024 tax rate in dollars per $100 of taxable value, empty when the unit did not exist or had no 2024 rate. |

### `data/north_carolina_tax_rates_2025_26.csv`

| Column | Description |
| --- | --- |
| `county_fips` | The county's five-digit Federal Information Processing Standards code. |
| `county` | The county name. |
| `municipality` | The municipality name or '(unincorporated)' for areas outside municipalities. |
| `county_rate_per_100` | The county tax rate in dollars per $100 of taxable value. |
| `municipal_rate_per_100` | The municipal tax rate in dollars per $100 of taxable value, empty for '(unincorporated)' rows. |
| `combined_rate_per_100` | The combined county and municipal rate in dollars per $100 of taxable value. |
| `effective_combined_rate_per_100` | The effective combined rate in dollars per $100 of taxable value, adjusted by the county's sales assessment ratio. |
| `previous_year_rate_per_100` | The 2024-25 rate in dollars per $100 of taxable value: the county rate on '(unincorporated)' rows and the municipal rate on municipality rows. |
| `last_reappraisal` | The year of the county's last property reappraisal. |

### `data/florida_millage_2025.csv`

| Column | Description |
| --- | --- |
| `county_fips` | The county's five-digit Federal Information Processing Standards code. |
| `county` | The county name. |
| `county_operating` | The 2025 county operating millage in mills, or dollars per $1,000 of taxable value (0 for Duval County, whose consolidated Jacksonville government levies it as a municipal rate). |
| `county_debt` | The 2025 county debt millage in mills, or dollars per $1,000 of taxable value, from the Florida Department of Revenue. |
| `county_dependent_districts` | The 2025 county dependent special district millage in mills, or dollars per $1,000 of taxable value. |
| `school_operating` | The 2025 school operating millage in mills, or dollars per $1,000 of taxable value, from the Florida Department of Revenue. |
| `school_debt` | The 2025 school debt millage in mills, or dollars per $1,000 of taxable value, from the Florida Department of Revenue. |
| `independent_districts` | The 2025 independent special district millage in mills, or dollars per $1,000 of taxable value. |
| `countywide_subtotal` | The sum of the county, school and special district millage that applies countywide, in mills. |
| `partial_county_levies_countywide_equivalent` | MSTU, municipal, and other levies applying only to part of the county, expressed as countywide-equivalent mills, or dollars per $1,000 of taxable value. |
| `total_mills` | The total 2025 millage in mills, or dollars per $1,000 of taxable value, from the Florida Department of Revenue. |
| `taxes_levied` | Taxes levied in US dollars in 2025, from the Florida Department of Revenue. |
| `levy_change_vs_2024_pct` | The percent change in taxes levied compared with 2024. |
<!-- columns:end -->

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
