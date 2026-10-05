## Chart 1: Variable-Width Column

**Tool:** ChatGPT\
**Model:** GPT-5.6 Sol\
**Date:** October 5, 2026

### Full Prompt

Create a variable-width column chart in R using the Happy Planet Index 2006–2025 dataset. Use 2025 data only. Each continent should be represented by one column, with column width proportional to population and column height equal to the mean HPI score for that continent. Use ggplot2 and `geom_rect()` with cumulative `xmin` and `xmax` values.

The chart should have a clear takeaway title, labelled axes with units, a source caption, and a color-blind-safe palette. Keep the design consistent with the other charts in the assignment. Make the chart readable in Quarto and pay special attention to label placement so that smaller continent groups are not overcrowded. If necessary, place labels above the bars and use connector lines.

### What I Fixed

The first version used the wrong population scaling because the dataset stores population in thousands. I corrected the axis conversion and adjusted the labels so the smaller continent columns were easier to read.

I also moved the labels above the bars and added connector lines to improve clarity.

## Chart 2: Table With Embedded Charts

**Tool:** ChatGPT\
**Model:** GPT-5.6 Sol\
**Date:** October 5, 2026

### Full Prompt

Create a table-style visualization in R using the Happy Planet Index 2006–2025 dataset. Use 2025 data and focus on the 20 most populous countries. Compare HPI, life expectancy, life satisfaction, and ecological footprint across countries.

The visualization should function like a table with embedded charts, using inline bars or a faceted layout that allows the indicators to be compared side by side. Use R only and keep the style consistent with the rest of the assignment. Include clear indicator labels, units where appropriate, a descriptive title, and a source caption. Make the output readable when rendered in Quarto.

### What I Fixed

The first approach used `gtExtras`, but it produced a package compatibility error. I replaced it with a `facet_wrap()` approach, which was also listed as an acceptable method in the assignment.

I also added units to the indicator headings and shortened the chart text for readability.

## Chart 3: Bar Chart

**Tool:** ChatGPT\
**Model:** GPT-5.6 Sol\
**Date:** October 5, 2026

### Full Prompt

Create a horizontal bar chart in R using the Happy Planet Index 2006–2025 dataset. Use 2025 HPI scores and display the 20 countries with the highest HPI scores and the 20 countries with the lowest HPI scores.

Sort the countries by HPI and clearly separate the top-20 and bottom-20 groups. Add HPI values at the ends of the bars. Use a clean, readable design with a descriptive title, labelled axis, source caption, and colors that are easy to distinguish. Keep the visual style consistent with the other charts and make sure the chart renders cleanly in Quarto.

### What I Fixed

I adjusted the spacing between the top-20 and bottom-20 panels and reduced the bar width to improve readability.

I also checked the ordering and added the HPI values directly to the bars.

## Chart 4: Column Chart

**Tool:** ChatGPT\
**Model:** GPT-5.6 Sol\
**Date:** October 5, 2026

### Full Prompt

Create a column chart in R using the Happy Planet Index 2006–2025 dataset. Use 2025 data and calculate the mean life satisfaction score for each continent.

Display one column per continent and sort the columns from highest to lowest mean life satisfaction. Add value labels above the columns and use a y-axis that clearly shows the 0–10 life satisfaction scale. Include a descriptive title, labelled axis with units, source caption, and a color-blind-safe palette. Keep the visual style consistent with the other charts in the assignment and make sure the output renders cleanly in Quarto.

### What I Fixed

I adjusted the continent labels and chart spacing to improve readability. I also checked that the axis label included the correct units and that the chart matched the overall visual style of the other figures.
