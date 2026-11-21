# Tracking Irrigation and Water Changes in Ethiopia’s Awash River Basin (2024–2025)

A practical remote sensing and statistical study built with Google Earth Engine, Python, and R.

## Why This Matters

In Ethiopia’s Afar Region, the Awash River is the main lifeline for agriculture, livestock, and local communities. During the dry months from October to March, reliable irrigation makes the difference between healthy harvests and severe water stress. However, ground monitoring across such a vast, hot, and remote landscape is expensive, and traditional optical satellites often miss key changes when haze or clouds pass over.

I built this project to solve that problem using free, open-access satellite radar data. By comparing two consecutive dry seasons (2024 and 2025), this study shows exactly where irrigation expanded, where crops grew stronger, and where surface water or soil moisture declined along the Awash River corridor.

## What I Did

To get a clear picture of the ground without atmospheric interference, I used Sentinel-1 Synthetic Aperture Radar (SAR) imagery inside Google Earth Engine. Radar waves pass right through clouds and measure surface roughness and moisture directly.

First, I filtered all descending Sentinel-1 radar passes covering the Afar Region across two dry seasons: October 2023 to March 2024, and October 2024 to March 2025. Radar images naturally contain graininess, so I combined each season using a median composite and applied a 30-meter smoothing filter to produce crisp, reliable layers.

Next, I subtracted the 2024 radar values from the 2025 values. This revealed the exact two-year shift in decibels (dB) across the entire basin. I grouped these changes into five clear categories:

1. Strong Decrease (below -2.5 dB): Areas that lost surface water, experienced receding floodplains, or had crops harvested.
2. Moderate Decrease (-2.5 to -1.0 dB): Land showing signs of soil drying or thinner vegetation cover.
3. Stable (-1.0 to +1.0 dB): Unchanged desert terrain, bare rock, and permanent structures.
4. Moderate Increase (+1.0 to +2.5 dB): Active crop growth and rising soil moisture.
5. Strong Increase (above +2.5 dB): New irrigation expansion, dense crop canopies, or wet soil.

Finally, I exported the exact area measurements in hectares and square kilometers to a CSV file and brought the data into R. Using R, I created a dual-axis combination chart that pairs the total land area in square kilometers with the percentage share of each category.

## Files in This Repository

afar_awash_change_map.png
A color-coded map of the Afar Region highlighting areas of new irrigation and wetting in red and orange, and areas of drying or water loss in blue.

afar_awash_change_stats.csv
The exported dataset showing exact area totals in hectares and square kilometers for every change category.

afar_awash_combination_chart.png
A statistical chart built in R displaying both the physical area (bars) and overall percentage share (line) for each category.

## Future Direction

This work demonstrates how cloud computing and open satellite data can support water resource engineering in regions with limited ground sensors. Moving forward, I plan to combine this radar workflow with Sentinel-2 optical vegetation data, CHIRPS rainfall records, and district-level water balance models to help local irrigation managers plan more efficiently for drought and climate variability.

## Author

Zedagim Tesfaye Tantu
Water Resources and Irrigation Engineer | Geospatial Data Analyst
Ethiopia
