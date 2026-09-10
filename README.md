# 2024 Sri Lankan Presidential Election — Power BI Dashboard

An interactive Power BI dashboard analyzing voting patterns, turnout, and regional political sentiment in the 2024 Sri Lankan presidential election — including the country's first-ever second-preference (ranked-choice) vote count.



---

## Overview

On 21 September 2024, Sri Lanka held its ninth presidential election with 38 candidates and over 17 million registered voters. Because no candidate crossed the constitutional 50% threshold, the Election Commission conducted the country's first-ever second-preference count to determine the winner.

This project cleans, models, and visualizes the full results dataset in Power BI to answer two core questions:

- How did voting patterns and party support vary across the 22 electoral districts?
- How did voter turnout differ from region to region, and what does that reveal about the election?

## Dashboard Preview

**National results and the district-level winner map**

![District results map](https://github.com/Kugashanth/Power_BI_Project/blob/main/dashboard_images/dashboard-district-map.png)

**Postal vote breakdown (officials and security personnel)**

![Postal votes](https://github.com/Kugashanth/Power_BI_Project/blob/main/dashboard_images/Dashboard%20postal%20votes.png)

**District drill-through view**

![District drill-through](https://github.com/Kugashanth/Power_BI_Project/blob/main/dashboard_images/Dashboard%20district%20drillthrough.png)

**All-island final result after the second-preference count**

![Final result](https://github.com/Kugashanth/Power_BI_Project/blob/main/dashboard_images/Dashboard%20final%20result.png)

## Key Features

- 🗺️ **Interactive choropleth map** of Sri Lanka, color-coded by leading candidate per district
- 🔍 **Drill-through pages** from national → district → polling-division level
- 🎚️ **Cross-filtering slicers** — clicking any district instantly updates all visuals (results table, turnout card, charts)
- 📊 **First-count vs. second-count comparison** showing how preferential votes changed the outcome
- 📮 **Postal vote breakdown**, isolating how public officials and security forces voted
- 📈 **Calculated DAX measures** for turnout %, valid vote %, rejected vote %, and per-candidate vote share

## Data Source

- Results data: [`govarthenan/2024-lka-pres-election-dataset`](https://github.com/govarthenan/2024-lka-pres-election-dataset) — a public GitHub repository scraping official results published by the Election Commission of Sri Lanka.
- Coverage: all 22 electoral districts, first-count and second-count (preferential) results, postal and general vote breakdowns.

## Data Preparation (Power Query)

| Step | Description |
|---|---|
| Standardize district names | Fixed inconsistent spelling/capitalization across all 22 districts |
| Handle missing values | Null postal-vote entries replaced with zero rather than removed |
| Fix data types | Converted comma-formatted vote counts from text to numeric |
| Calculated columns | Turnout %, valid %, rejected %, and vote share per candidate |
| Data modeling | Related results table to a Sri Lanka district geography table for map and drill-through visuals |

## Key Insights

1. **Historic second-count win** — First-count leader Anura Kumara Dissanayake (42.31%) was confirmed winner only after the second-preference count, finishing at 55.89% vs. 44.11%.
2. **Postal vote divergence** — Officials and security personnel favored Dissanayake even more strongly (56.69%) than the general electorate.
3. **Regional divide** — The Tamil-majority Jaffna district voted sharply differently from the national trend: Dissanayake polled just 8.82% there, while minority-aligned "Others" led with 33.97%.
4. **Turnout gap** — National turnout was 79.46%, but conflict-affected northern districts like Jaffna and Mullaitivu recorded the lowest turnout island-wide.

## Tech Stack

- **Power BI Desktop** — dashboard design and DAX measures
- **Power Query (M)** — data cleaning and transformation
- **GitHub** — dataset sourcing

## Project Structure

```
├── Datasets/               # Raw and cleaned election result data files
├── District PNGs/          # District-level map images (raster)
├── Divisions PNGs/         # Polling division map images (raster)
├── Divisions SVG Files/    # Polling division map images (vector)
├── Power BI Dashboard/     # .pbix dashboard file(s)
├── Sri Lanka Map GeoJSON/  # GeoJSON boundary files used for the map visual
└── dashboard_images/       # Exported dashboard screenshots
```

## How to Use

1. Clone this repository.
2. Open `dashboard.pbix` in [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
3. If prompted, refresh the data source to point to your local copy of the dataset.
4. Explore the report pages using the slicers and drill-through buttons.

