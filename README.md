# Bloomberg Covid-19 Vaccine Tracker Open Data

## Terms of Use

By downloading the Dataset, you agree that you will attribute the Dataset and any use of the Dataset to Bloomberg. You may use the Dataset for personal or internal business purposes, and may make limited use of the Dataset in connection with the provision of other services to clients; provided that you may not monetize the Dataset or otherwise make commercial use of the Dataset where the Dataset constitutes all, or substantially all, of the commercial offering. The Dataset is provided “as-is” and without any express or implied warranties.

## Dataset Description

[The Bloomberg Covid-19 Vaccine Tracker](https://www.bloomberg.com/graphics/covid-vaccine-tracker-global-distribution/) covers all U.S. states and territories as well as a growing number of countries internationally, on a daily basis. Vaccination data has been gathered from government websites, official statements and Bloomberg interviews, as well as third-party sources including the World Health Organization, Johns Hopkins University and Our World In Data. In the U.S., prior to Feb. 20, 2021 when local governments and the Centers for Disease Control and Prevention reported different totals for the same jurisdiction, Bloomberg used the higher number (unless there was a data quality concern). Starting on Feb. 20, 2021 CDC data is used exclusively for the U.S. due to methodological changes that disallow comparison with state-reported data. It may take several days for counts to be reported to databases.

## Updating

The latest raw data will be pushed to this repository once a day.

The file [UPDATED.txt](data/UPDATED.txt) indicates the time at which the data was last acquired from our data store.

## Data Dictionary

These comma-separated values (CSV) files are available for download, with the following data fields.

[current-global.csv](data/current-global.csv) – Snapshot of the latest global update to the Bloomberg Covid-19 Vaccine Tracker

* `id`: ISO 3166-1 alpha-3 country code (full list available [here](https://unstats.un.org/unsd/tradekb/knowledgebase/country-code)). Subdivisions are also standard ISO codes (ISO 3166-2 alpha-2 or alpha-3), unless otherwise specified. London’s (GBR-LON) is a non-standard code.
* `name`: Jurisdiction name in Bloomberg style.
* `population`: 2020 national population figures or estimates from the International Monetary Fund [October 2021 World Economic Outlook](https://www.imf.org/en/Publications/WEO/weo-database/2021/October).
* `dosesAdministered`: Cumulative number of vaccine doses administered.
* `peopleVaccinated`: Cumulative number of people who’ve received at least one dose.
* `completedVaccination`: Cumulative number of people who’ve been fully vaccinated with either a single-, two- or three-dose vaccine.
* `boosterDosesAdministered`: Cumulative number of additional doses administered to people who've already been fully vaccinated with either a single-, two- or three-dose vaccine.

[current-usa.csv](data/current-usa.csv) – Snapshot of the latest U.S. update to the Bloomberg Covid-19 Vaccine Tracker

* `id`: Postal abbreviations for states, territories and vaccination jurisdictions (full list available [here](https://faq.usps.com/s/article/What-are-the-USPS-abbreviations-for-U-S-states-and-territories)). Cities and federal entities are given non-standard identifiers, e.g. “new-york-city”.
* `name`: State, territory, city or vaccination jurisdiction name.
* `population`: Population figures are from the [U.S. 2020 Census](https://www.census.gov/library/stories/state-by-state.html) for the U.S. and Puerto Rico, as well as [U.S. island territories](https://www.census.gov/library/stories/2021/10/first-2020-census-united-states-island-areas-data-released-today.html). Latest estimates from the CIA Factbook are used for Micronesia, Palau and the Marshall Islands.
* `dosesAdministered`: Cumulative number of doses administered in a state, regardless of residency. This is the administration data published on our website. Prior to Feb. 20, 2021 it includes the most up-to-date figures drawn from the CDC and from state-run dashboards—whichever value is higher; CDC data, which includes doses administered by federal entities within each state as of Feb. 20, 2021 is currently used.
* `peopleVaccinated`: Cumulative number of a state's residents who’ve received at least one dose; prior to Feb. 20, 2021 this refers to people who were vaccinated in a state, regardless of residency. (Note: if higher than the CDC number prior to Feb. 20, 2021 state-reported data is used.)
* `completedVaccination`: Cumulative number of a state's residents who’ve been fully vaccinated with either a single- or two-dose vaccine; prior to Feb. 20, 2021 this refers to people who were fully vaccinated in a state, regardless of residency. (Note: if higher than the CDC number prior to Feb. 20, 2021 state-reported data is used.)
* `completedOneDoseVaccination`: Cumulative number of a state's residents who’ve been fully vaccinated with a single-dose vaccine.
* `boosterDosesAdministered`: Cumulative number of additional doses administered to people who've already been fully vaccinated with either a single- or two-dose vaccine.
* `cdcDosesDistributed`: Cumulative number of vaccine doses delivered, according to the CDC. (Data for New York City is as reported by the city.)

[historical-global-doses-administered.csv](data/historical-global-doses-administered.csv) – Cumulative number of doses administered by country

* `id`: ISO 3166-1 alpha-3 country code (full list available [here](https://unstats.un.org/unsd/tradekb/knowledgebase/country-code)). Subdivisions are also standard ISO codes (ISO 3166-2 alpha-2 or alpha-3), unless otherwise specified. London’s (GBR-LON) is a non-standard code.
* `date`: Date on which new datapoint was recorded by Bloomberg. (Note: all areas are checked daily, but depending on when the source is updated it may have been recorded with a day or more of lag.)
* `value`: total number of doses administered (e.g. `dosesAdministered`) as recorded on that date.

[historical-usa-doses-administered.csv](data/historical-usa-doses-administered.csv) – Cumulative number of doses administered by U.S. states, territories or other vaccination jurisdictions

* `id`: Postal abbreviations for states, territories and vaccination jurisdictions (full list available [here](https://faq.usps.com/s/article/What-are-the-USPS-abbreviations-for-U-S-states-and-territories)). Cities and federal entities are given non-standard identifiers, e.g. “new-york-city”.
* `date`: Date on which new datapoint was recorded by Bloomberg. (Note: all areas are checked daily, but depending on when the source is updated it may have been recorded with a day or more of lag.)
* `value`: Total number of doses administered (e.g. `dosesAdministered`) as recorded on that date. Starting on Feb. 20, 2021 this is the CDC number for doses administered, including by any federal entities in a given state; prior to that, this was the higher of of the state-reported or CDC-reported figure and excluded federal entities.

## Country Notes

* Brazil: Data prior to July 1,2021 covers most but not all states, as explained in this [blog post](https://www.bloomberg.com/news/live-blog/2021-01-21/methodology-and-analysis-for-the-covid-19-vaccine-tracker#6012F60FB2240001).
* U.K.: National figures are calculated as the sum of country-level data, rather than directly reported. Crown dependencies and British Overseas Territories are excluded from U.K.’s total.
* U.S.: Prior to Feb. 20, 2021 national figures are calculated as the sum of states, the District of Columbia, territories, federal agencies and the Pacific Island nations that are covered by the U.S. vaccination drive (Marshall Islands, Micronesia, Palau). Starting Feb. 20, 2021 the numbers reported by the CDC are used.
