# Indonesia Tourism Dashboard

An interactive Power BI dashboard exploring ~437 tourist attractions across 
5 major Indonesian cities (Jakarta, Bandung, Semarang, Surabaya, Yogyakarta), 
built on a public Kaggle dataset originally created for the Bangkit Academy 
2021 "GetLoc" capstone project.

## Live Report
https://github.com/zrchew/indonesia_tourism_dashboard

## Dataset
- Source: https://www.kaggle.com/datasets/aprabowo/indonesia-tourism-destination
- `tourism_with_id.csv` — attraction-level data: name, description, category, price, 
  rating, coordinates, visit duration
- `package_tourism.csv` — curated multi-stop route bundles 
- `tourism_rating.csv` / `user.csv` — synthetic/dummy data on the age of tourists visiting the attractions and the corresponding ratings given to those attractions
- `place_translations.csv` — self created spreadsheet to translate places names into English

## Pages
1. **Overview** — national, cluster, and individual-attraction KPIs (number 
   of attractions, average price, average rating); map of all attractions; 
   category breakdown; searchable attraction slicer
2. **City Deep-Dive** — per-city KPIs (number of attractions, average price, 
   average rating); category mix; price-tier distribution; top-rated 
   attractions table; price and rating filters
3. **Price vs. Value** — scatter analysis of price vs. rating; <surfaces that 
   higher price doesn't reliably predict higher rating> ; best-value and 
   splurge-worthy picks per city

## How to Explore
- Use the **city slicer** on City Deep-Dive and Price vs. Value to filter 
  everything on that page to a single city.
- On **Overview**, click any map bubble, or use the searchable attraction 
  slicer, to filter the KPI cards down to a specific attraction.
- On **City Deep-Dive**, use the price and rating filters to narrow the 
  top-rated attractions table to your budget or quality threshold.
- On **Price vs. Value**, hover over any point on the scatter chart to see 
  the exact price and rating for that attraction, and view recommendations for best value and attractions worth splurging for

## Key techniques used
- Custom price-tier bucketing via calculated columns (Free / Budget / 
  Mid-range / Premium / Luxury)
- Dynamic KPI cards responding to slicer and map-click cross-filtering
- Custom report-page tooltips for map hover detail
- DAX measures for value scoring (rating-to-price relationship)

## Known limitations
- **Synthetic user/rating data**: `tourism_rating.csv` and `user.csv` contain 
  dummy/randomly generated values, not real visitor behavior. This project can have a better reccomendation system built if real data is provided
- **Price distribution is heavily skewed**: ~31% of attractions are free 
  (Price = 0), which pulls simple averages downward and required custom 
  price-tier bucketing (rather than even-width bins) to produce a meaningful 
  distribution chart.
- **Ties in rating-based rankings**: "top-rated attractions" tables can 
  include more rows than a strict cutoff (system is set to top 10) when multiple 
  places share the exact same rating as ties in rating are shown rather than arbitrarily 
  cut.

## Tools
Power BI Desktop, DAX, Power Query (M)