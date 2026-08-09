# Basotho Wool Dataset Cleaning & Exploratory Data Analysis

## Project Overview
Cleaned, analyzed, and visualized the **Basotho Wool trade dataset** to understand export trends, seasonal patterns, and the relationship between trade value and export volume over time. The workflow demonstrates **data inspection, preprocessing, and multi-chart exploratory analysis**.

---

## Dataset
- **Source:** TidyTuesday - Basotho Wool CSV
- **Rows/Columns:** 293 rows, 24 columns
- **Key Features:** `ref_year`, `ref_month`, `net_wgt`, `cifvalue`, `fobvalue`, `qty`, `qty_unit_abbr`, `alt_qty`, `flow_code`

---

## Workflow & Detailed Steps

### 1. Data Inspection
- Loaded dataset using pandas
- Checked dataset shape, column types, and unique values
- Identified missing values in `cifvalue`, `fobvalue`, `qty_unit_abbr`, `alt_qty_unit_abbr`, `qty`, and `alt_qty`

### 2. Data Cleaning
- Dropped rows where both `cifvalue` and `fobvalue` were missing simultaneously
- Filled missing `cifvalue` using `fobvalue` from the same row and vice versa
- Filled missing `qty_unit_abbr` and `alt_qty_unit_abbr` with `"unknown"`
- Filled missing `qty` and `alt_qty` with column median
- Confirmed all columns returned zero missing values post-cleaning

### 3. Visualization & Analysis

**Chart 1 - FOB Trade Value Over Time (Line Chart)**
- Grouped data by year and summed total FOB value
- Plotted yearly trend from 2010 to 2024

**Chart 2 - Net Weight Exported Over Time (Line Chart with Markers)**
- Grouped data by year and summed total net weight
- Added markers at each data point for clarity

**Chart 3 - Exports by Month (Bar Chart)**
- Grouped data by month and summed total net weight
- Revealed seasonal export patterns across the calendar year

---

## Skills Demonstrated
- **Data Analysis & Exploration:** pandas, matplotlib, seaborn
- **Data Cleaning & Preprocessing:** missing value handling, cross-column imputation, median filling
- **Data Visualization:** line charts, bar charts, markers
- **Exploratory Data Analysis:** trend analysis, seasonality, volume vs value comparison
- **Workflow Management:** end-to-end dataset cleaning and visualization in Jupyter Notebook

---

## Outputs & Insights
- Cleaned dataset free of all missing values
- Basotho wool FOB trade value grew approximately **30x from 2010 to 2022**
- Export volume growth confirmed as the **primary driver of value increase**, not price alone
- A significant export crash occurred in **2017-2018**, likely linked to regional drought in Lesotho
- Clear seasonal pattern identified — exports peak in **November and January**, aligned with the Southern Hemisphere shearing calendar
- July and August consistently record the **lowest export volumes** corresponding to Lesotho's winter
