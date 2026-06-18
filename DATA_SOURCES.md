# Data Sources & Attribution

The MIT `LICENSE` in this repository covers the **compilation, processing, and
formatting** of these datasets (the scripts and the cleaned/normalized CSVs as
arranged here).

The **underlying data** originates from Government of India / public sources.
Those original sources retain their own rights and terms (typically the
Government Open Data License – India (GODL) or equivalent). Please credit the
original sources when you reuse this data, and consult the original portals for
the authoritative, most current figures.

## `cce_yield/crop_cutting.csv`
- **What:** Crop Cutting Experiment (CCE) yield observations from the General
  Crop Estimation Survey (GCES). Point-level crop yield by district / sub-district
  / village (LGD codes), crop, season, and year (2023–2024), with WGS84 coordinates.
- **Original source:** Government of India crop estimation survey programme
  (Ministry of Agriculture & Farmers Welfare / DA&FW, GCES/CCE).
- **Geometry:** `geom_wkt_wgs84` column is reprojected from the source
  EPSG:32643 to EPSG:4326 (WGS84). Raw `latitude`/`longitude` columns are
  retained as-supplied.

## `mandi_prices/agmarknet_crop_prices_monthly.csv`
- **What:** Monthly market (mandi) prices aggregated by commodity × state ×
  month — modal/min/max average prices with standard deviation and record counts.
- **Original source:** Agmarknet (Directorate of Marketing & Inspection,
  Department of Agriculture & Farmers Welfare, Ministry of Agriculture &
  Farmers Welfare, Government of India).

## `mandi_prices/msp_food_grains.csv` & `mandi_prices/msp_non_food_grains.csv`
- **What:** Minimum Support Prices (MSP) by crop category and fiscal year,
  used as a price fallback where market data is unavailable.
- **Original source:** Commission for Agricultural Costs and Prices (CACP) /
  Ministry of Agriculture & Farmers Welfare, Government of India.

---

*No warranty is made as to the accuracy or completeness of this data. See `LICENSE`.*
