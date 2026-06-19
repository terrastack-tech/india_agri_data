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

## `mandi_prices/agmarknet_crop_prices_daily.csv.gz`
- **What:** Daily market (mandi) prices by commodity × state — min/max/modal
  price per day (`Rs/Quintal`). Columns: `t` (date), `cmdty`/`commodity_name`,
  `state`/`state_name`, `state_id`, `commodity_id`, `category_id`, `p_min`,
  `p_max`, `p_modal`. Covers 2020-04-01 to 2025-03-31 (~2.07M rows, 361
  commodities, 31 states). gzip-compressed (~199 MB uncompressed).
- **Granularity note:** Prices are daily, aggregated to the **state** level
  (across all markets within a state); there is no per-market/per-district
  breakdown in this file. The `monthly` file below is a month-level rollup of
  this same data.
- **Original source:** Agmarknet (Directorate of Marketing & Inspection,
  Department of Agriculture & Farmers Welfare, Ministry of Agriculture &
  Farmers Welfare, Government of India).

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
