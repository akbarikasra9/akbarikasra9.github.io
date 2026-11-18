# Texas Change Atlas: Are Immigrant Families Catching Up in Texas?

## Question

This is aimed at members of the legislative services in Texas and those working in local workforce boards. However, this can be used by anybody interested in knowing how their county is doing. This project was aimed at finding out whether immigrant families are catching up to natives in Texas. This was done by comparing wages, bachelor degree attainment, and unemployment rates. We also asked whether the answer would change if we were looking at the children of the immigrants, males vs females, people with and without a degree, and how it differed between Houston and smaller western counties. This turned out to be quite controversial. Abramitzky and co-authors (2021) found that immigrant children do move up the income ladder. Villarreal and Tamborini (2023) found that second generation hispanic males fall further behind as they age. We felt it was a good idea to look at this within Texas. We decided as a rule of thumb that we would use data with a margin of error (MOE). Only if the difference between the two groups we were looking at went beyond the 90% MOE of the data would we say that there was closing or widening. If not, we would say there was no clear change.

## Data

We used three data sources as we couldn't get all the information we needed from one. First we needed to look at locations so we used Table S0501 from the American Community Survey (ACS) 5 year estimates by the Census Bureau. This gave us county level data on all 254 counties in Texas. We looked at comparisons between 2015-2019 and 2020-2024. We split this data into those born in the US and those born abroad. We also looked at wages, degree attainment, unemployment and population. This data had MOE's already included which helped us. We also sorted the counties into big metropolitan, smaller metropolitan, and rural areas using the USDA Rural-Urban Continuum Codes 2023. Next we needed data on individuals to look at how fast they were moving up. We used microdata from the ACS one year estimates from IPUMS USA v16.0. We used the data from 2015-2019 and 2021-2024. We couldn't use 2020 as it was only released as experimental data from the census due to COVID. Using this data we could look at those who immigrated as adults between 1980-2019. We looked at how their wages improved depending on how long they had been in the country by looking at the five year cohorts they arrived in. Finally we used the CPS Annual Social and Economic Supplement (CPS ASEC) from IPUMS CPS v13.0. As there were only a small number of people in Texas we combined them into two sets of data, 2015-2019 and 2022-2024. This survey also asked where their parents were born meaning we could split them into first generation (born abroad), second generation (born in the US and have at least one immigrant parent), and third generation or higher. We only used people aged between 25-54 from both individual data sets and only looked at those in full time work throughout the year.

## Variables

We have used one simple variable for wages. We divided the median earnings of a group by the median of the group we were comparing and multiplied by 100. This tells us if they have equal wages (100) or less (85 would mean they earn 85 cents for every dollar). Degrees and unemployment are simply the difference between the two groups in percentages. Any variables with less than 100 people or where the error rate is over 30% of the estimate will be displayed as faded and have the note ‘Use with Caution’. We didn’t want people to believe too much in unreliable data. If you want to see the details of the variables (codes, what group they are being compared to, how we got standard errors) we have detailed them in METHODS.md.

## Visualisations (Abela, 2006)

We used Abela’s Chart Suggestions Thought-Starter to decide what charts to use. Chart 1 is a bubble chart (18). Each bubble represents a county. As we move from left to right the proportion of people born abroad increases. Up and down shows us the gap in 2020-2024. The size of the bubble shows us the population, we can tell if it is a metropolitan or rural area from the shape of the bubble, and the colour shows us whether the gap closed, widened or stayed the same. Chart 2 is a scatter plot (9). It shows us how the wage score of each group changed from the previous to the current time. There are 8 groups (first/second gen, with/without degree, male/female). If the bubble moved closer to the equal line they have improved. Chart 3 is a line chart (6). Each line shows how the wage score of each arrival cohort has changed over time. If the line is increasing it means they are catching up. Chart 4 is a dumbbell chart. This is essentially a bar chart (3). It shows us the degree and unemployment gap between first and second generation males and females. The line between the two bubbles makes it stand out how much it has changed. We also added a map. Abela didn’t include maps so we haven’t given it a number. We have still used the same colours as chart 1.

## Interactivity

We have created a Quarto dashboard. This has three pages; location, who, and how fast. On the map page we can switch between wages, degrees and unemployment. We have also included a map and search bar to help people find their county. When clicking on a group in the legend it will hide. Hovering over a point will show you the exact value, 90% MOE and how many people it is based off. We have included some key values at the top. All the unreliable estimates are faded.

## Deployment

We have deployed this on GitHub Pages. This is free to use and means we don’t have to worry about our server. It also fits into our course website. We have created everything in R using tidyverse, tidycensus, ipumsr, sf, plotly, and DT. The visualisations and search table have been created in the browser meaning we can have interactive visuals without a server. IPUMS won’t allow anyone to repost their raw data so we have provided our code and extract definitions. Anyone with a free IPUMS account can recreate the entire dashboard. Please note that this is showing trends and not causation. Immigrants who aren’t improving their wages are more likely to leave the country (Akee, Chin, and Crown, 2026). This means they appear to be catching up quicker. Also we only ever show birthplace. Knowing someone was born abroad gives us no information about their legal status. We don’t report this.

## References

Abela, A. (2006). Chart suggestions: A thought-starter. Extreme Presentation.

Abramitzky, R., Boustan, L., Jácome, E., and Pérez, S. (2021). Intergenerational mobility of immigrants in the United States over two centuries. American Economic Review, 111(2), 580–608.

Akee, R., Chin, J., and Crown, D. (2026). Immigrant earnings assimilation, 1981–2021 (Working Paper 2026-04). Congressional Budget Office.

Flood, S., et al. (2025). IPUMS CPS: Version 13.0 [Data set]. IPUMS. https://doi.org/10.18128/D030.V13.0

Ruggles, S., et al. (2025). IPUMS USA: Version 16.0 [Data set]. IPUMS. https://doi.org/10.18128/D010.V16.0

U.S. Census Bureau. (n.d.). American Community Survey 5-year estimates, Table S0501, 2015–2019 and 2020–2024 [Data set]. https://data.census.gov

U.S. Department of Agriculture, Economic Research Service. (2024). 2023 Rural-Urban Continuum Codes [Data set]. https://www.ers.usda.gov/data-products/rural-urban-continuum-codes

Villarreal, A., and Tamborini, C. R. (2023). The economic assimilation of second-generation men: An analysis of earnings trajectories using administrative records. Demography, 60(5), 1415–1440. https://doi.org/10.1215/00703370-10924116

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Assignment 9: Spatial Mapping Plan

## 1. Geographic Units and Boundaries

The Texas Change Atlas examines geographic differences between foreign-born and native-born Texans across all 254 Texas counties.

Each geographic unit represents one county, identified by its five-digit Federal Information Processing Standards (FIPS) code, stored as `GEOID`.

County-level data are stored in `county_change.csv`, while geographic boundaries are stored in `tx_counties.rds`. These datasets are joined using `GEOID`, which provides a consistent geographic identifier.

The spatial join preserves all 254 Texas county boundaries, including counties without available estimates. Missing values are displayed separately rather than replaced with estimated values.

The boundary file originates from the existing Texas Change Atlas project. Its original geographic source should be documented alongside the dataset.

## 2. Variables and Mapping Methods

The project examines three principal measures:

| Variable | Measurement type | Units | Visualization |
|---|---|---|---|
| Earnings score | Index | 100 represents equal earnings | Choropleth |
| College degree gap | Difference between shares | Percentage points | Choropleth |
| Unemployment gap | Difference between rates | Percentage points | Choropleth |
| County population | Count | Residents | Proportional symbols |

The choropleth maps use normalized measures to compare counties. County population is represented using proportional symbols because it measures an absolute count rather than a rate or index.

The dashboard also examines reported changes between the 2015–2019 and 2020–2024 ACS measurement periods.

For change-focused maps, teal represents narrowing differences, coral represents widening differences, and gray represents no clear change. Darker colors indicate larger observed changes within their reported classifications.

Counties with insufficient estimates or reliability concerns are identified separately. The original reported classifications are preserved without inventing additional statistical significance results.

## 3. Coordinate Reference Systems

Three coordinate reference systems are used:

**EPSG:4326 — Geographic coordinates**

County boundaries are stored or transformed to longitude and latitude coordinates. This format provides compatibility with geographic datasets and Leaflet.

**EPSG:5070 — NAD83 / Conus Albers Equal Area**

This projection is used for static Texas maps because it preserves relative area across the contiguous United States. It is appropriate for comparing county geography without the area distortion associated with Web Mercator.

**EPSG:3857 — Web Mercator**

Leaflet displays interactive maps using Web Mercator. The application supplies county geometries in EPSG:4326, which Leaflet projects for browser display.

The static mapping exercise also compares EPSG:4326, EPSG:3857, and EPSG:5070 to demonstrate how projections influence geographic appearance.

## 4. Interactive Map and Dashboard

The reactive map is incorporated into the Texas Change Atlas Shiny dashboard, extending the visualizations developed for Assignment 8.

The dashboard allows users to explore county-level differences through several interactive controls:

- **Indicator:** Select earnings, college degree gap, or unemployment gap.
- **County classification:** Filter counties by the available metro/rural categories.
- **Measurement period:** Select 2015–2019 or 2020–2024 as the reference period for summary values.
- **Map navigation:** Zoom and explore individual county boundaries, including detailed Dallas–Fort Worth and Houston views.

A shared Shiny `reactive()` dataset controls the geographic observations displayed on the map, summary statistics, and companion chart.

The dashboard updates the number of counties with available data, the number with missing values, the median of the selected measure, and a chart highlighting counties with large reported changes.

County popups provide additional information, including the county name, reported values, observed change, county classification, and data-quality qualifications.

Data and geographic boundaries are loaded and joined outside the Shiny server to avoid unnecessary repeated processing.

## 5. Data Sources and Limitations

The primary county-level data come from the U.S. Census Bureau's American Community Survey (ACS), including Table S0501, for the 2015–2019 and 2020–2024 measurement periods.

County classifications use the USDA Rural-Urban Continuum Codes.

Some counties do not have available estimates for every variable. These missing observations are preserved and identified rather than removed or imputed.

The maps describe geographic patterns and reported differences between measurement periods. They do not establish causal relationships.

Reported change classifications are maintained from the existing analysis. The mapping application does not independently recalculate statistical significance or margins of error when the necessary underlying information is unavailable.

## 6. Assignment Deliverables

The Assignment 9 deliverables are:

- **Part A:** This spatial mapping plan in `PLAN.md`.
- **Part B:** Static maps published through `maps.qmd`, including the spatial join, projection comparison, choropleth, classification comparison, and proportional-symbol map.
- **Part C:** A reactive Leaflet map within the Texas Change Atlas Shiny dashboard, deployed through Posit Connect Cloud and embedded on the project website.

The source code and supporting datasets are maintained in the project repository to support transparency and reproducibility.
