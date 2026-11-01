# Preliminary analysis of accident records involving e-scooters in New York City, 2021–2025 — 01/2021 to 12/2025

This repository contains data, analytic code, and findings that support portions of the article, “Brooklyn tops the list of boroughs with the highest number of e-scooter accidents, per preliminary analysis" (https://docs.google.com/document/d/1rg5dNMArPqWmPqyTE8Z4byfEeGxUzs3bfFwnqc81xIQ/edit?tab=t.0),” published 10, 30, 2026. Please read that article, which contains important context and details, before proceeding.

## Data

This analysis uses spreadsheets from filtered data from Motor Vehicle Collisions - Crashes and Motor Vehicle Collisions - Vehicles from Open Data.

The spreadsheets come from the following sources:

- Name of source:
  - [Download E-scooter dataset](./Data/Collisions_E-scooter_2021_2025.csv) Raw data of Motor Vehicle Collisions - Vehicles
  - `[NYC Collisions dataset (2021–2025)](./Data/nyc_collisions_2021_2025.csv.csv) Raw data of Motor Vehicle Collisions - Crashes
  [Download original filtered dataset (.gz)](./Data/nyc_collisions_2021_2025.csv.csv.gz) - Compressed dataset
  

Each of the spreadsheets contain, among others, the following columns relevant to the analysis:

- `COLLISION_ID` — Unique identifier for each collision or crash event in New York City, from 2021-2025
- `VEHICLE_TYPE` — Vehicle category, used to identify e-scooters.
- `BOROUGH` — NYC borough where the collision was recorded.




## Methodology

The notebook [`Preliminary_analysis_escooters.ipynb`](Notebooks/Preliminary_analysis_escooters.ipynb) performs the following analyses:

##### Part 1: Cleaning and sorting

- Filtered both datasets — Motor Vehicle Collisions – Vehicles and Motor Vehicle Collisions – Crashes — to include records from 2021 through 2025.

Filtered the Vehicles dataset to identify records corresponding to e-scooters.

Standardized vehicle type categories by grouping different labels referring to e-scooters under a single E-Scooter category.


##### Part 2: Merging and analyzing 

- Matched the e-scooter records with the Crashes dataset using COLLISION_ID.

Retrieved the borough information associated with each collision.

Grouped collisions by borough and counted unique COLLISION_ID values.

Sorted the results to identify the borough with the highest recorded number of e-scooter crashes.


## Outputs

The output folder contains the CSV file with the number of unique e-scooter crashes by borough: [E-scooter crashes by borough](./Output/escooter_crashes_by_borough.csv).

## Limitations
A total of 1,473 unique collision IDs had no borough recorded in the crash dataset. These cases were excluded from the borough ranking.

Therefore, the findings reflect collisions with an identified borough and should not be interpreted as a complete count of all e-scooter crashes in NYC.

## Running the analysis yourself

You can run the analysis yourself. To do so, you'll need the following installed on your computer:

- Python 3
- The Python libraries specified in [`requirements.txt`](requirements.txt)

## Licensing

All code in this repository is available under the [MIT License](https://opensource.org/licenses/MIT). The data file in the output/ directory is available under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0) license. All files in the data/ directory are released into the public domain.

## Feedback / Questions?

Contact YOUR NAME HERE at claudia.alizo81@journalism.cuny.edu
