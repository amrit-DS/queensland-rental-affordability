# Queensland Rental Affordability Analysis (2016–2021)

An analysis of how rental affordability for 2-bedroom flats changed across Queensland postcodes between the 2016 and 2021 Censuses.

## Key Finding

Median rental affordability across well-supported Queensland postcodes slightly improved from 21.7% in 2016 to 20.8% in 2021, as household income growth outpaced rental increases. The change was geographically uneven: affordability improved mainly across Brisbane and its surrounds, while it worsened on the Gold Coast, Sunshine Coast, and regional coastal centres such as Cairns, Mackay and Gladstone, consistent with pandemic-era population movement out of the capital toward the coast. Of the 124 well-supported postcodes, 67 improved and 54 worsened.

## Data Sources

1. **RTA Quarterly Median Rents:** Official government tenancy data detailing median weekly rent values and newly lodged bonds, grouped by postcode and dwelling type.
2. **ABS Census 2016 and 2021, G02 Tables:** Official government data capturing median total weekly household income across Queensland Postal Areas (POA).
3. **matthewproctor Postcode Dataset:** A community-sourced geographic file used to map latitude, longitude, and regional names to postcodes. Used only for geographic labelling, not for any analytical claim.

## Method

- **Target Segment:** 2-bedroom flats, chosen as a standard entry-level benchmark, where affordability pressure concentrates on lower-income and younger renters.
- **Temporal Alignment:** The September quarter was used to match the timing of the August ABS Census.
- **Affordability Metric:** Calculated using median household income rather than individual income, as rent is paid at the household level.
- **Rent Source:** RTA bond data was used rather than the Census's self-reported rent, because new bond lodgements reflect actual current market rents for new leases.
- **Data Integration:** An initial set of 143 postcodes with complete data in both years was isolated (postcodes missing either year were dropped, since a change cannot be computed without both).
- **Thin-Data Exclusion:** Postcodes with fewer than 10 new bonds in either quarter were excluded to remove unreliable medians built on small samples, leaving 124 well-supported postcodes.

## Limitations

- **Household Type Mismatch:** The income figure is the median for all households in a postcode, not specifically flat-renting households, so the ratio is an affordability proxy rather than a measure of the exact people in those flats.
- **Historical Horizon:** The analysis ends at the 2021 Census. The sharp post-2021 rental surge is not captured, as matching income data does not yet exist.
- **Geographic Coverage:** Low-volume postcodes were excluded by the thin-data rule, so the analysis is strongest for urban and coastal centres and silent on sparse remote areas, where few flats are rented.
- **Data Validation:** The community geographic file contained a broken region column (it labelled every postcode the same region). The correct column was identified and validated against known postcodes before use.

## How to Reproduce

1. Download the three source files:
   - RTA rental bond statistics spreadsheet.
   - ABS 2016 and 2021 General Community Profile table G02 zip folders for Queensland Postal Areas.
   - The matthewproctor community postcode geography file.
2. Open the Jupyter notebook (`queensland_rental_affordability.ipynb`).
3. Upload the source files to your runtime, or place them in your working directory. The geography file is downloaded automatically within the notebook.
4. Run the cells top to bottom to clean the data, apply the thin-data filter, compute the affordability ratios, validate the geography, and render the interactive map.
