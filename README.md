# indonesia\_tourism\_dashboard



\# Indonesia Tourism Dashboard



An interactive Power BI dashboard exploring \~437 tourist attractions across 

5 major Indonesian cities (Jakarta, Bandung, Semarang, Surabaya, Yogyakarta), 

built on a public Kaggle dataset originally created for the Bangkit Academy 

2021 "GetLoc" capstone project.



\## Live Report

https://github.com/zrchew/indonesia\_tourism\_dashboard



\## Dataset

\- Source: https://www.kaggle.com/datasets/aprabowo/indonesia-tourism-destination

\- `tourism\_with\_id.csv` — attraction-level data (real): name, category, price, 

&#x20; rating, coordinates, visit duration

\- `package\_tourism.csv` — curated multi-stop route bundles (real)

\- `tourism\_rating.csv` / `user.csv` — synthetic/dummy data (fake users and 

&#x20; ratings), used only for the Recommendation demo page. \*\*Not real visitor 

&#x20; behavior.\*\*



\## Pages

1\. \*\*Overview\*\* — national KPIs, map of all attractions, category breakdown, 

&#x20;  searchable attraction lookup

2\. \*\*City Deep-Dive\*\* — per-city KPIs, category mix, price-tier distribution, 

&#x20;  top-rated attractions table

3\. \*\*Price vs. Value\*\* — scatter analysis of price vs. rating; surfaces that 

&#x20;  higher price doesn't reliably predict higher rating; best-value and 

&#x20;  splurge-worthy picks per city

4\. \*\*Route/Package\*\* — browse pre-bundled multi-stop attraction packages by city

5\. \*\*Recommendation\*\* — simplified content-based suggestion demo (clearly 

&#x20;  labeled as using simulated rating data, not real user behavior)



\## Key techniques used

\- Custom price-tier bucketing via calculated columns (Free / Budget / 

&#x20; Mid-range / Premium / Luxury)

\- Dynamic KPI cards responding to slicer and map-click cross-filtering

\- Custom report-page tooltips for map hover detail

\- DAX measures for value scoring and simple recommendation ranking



\## Known limitations

\- Rating/visitor data in `tourism\_rating.csv` and `user.csv` is synthetic — 

&#x20; the Recommendation page is a methodology demo, not a real personalization 

&#x20; engine.

\- \[Any other caveats to be filled in — e.g., Place\_Id gaps, category translation 

&#x20; inconsistencies]



\## Tools

Power BI Desktop, DAX, Power Query (M)

