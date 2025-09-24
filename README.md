# Insurance Analytics Dashboard — Power BI

## Project summary

This Power BI report (`PrismDashboard.pbix`) is an interactive **Insurance Analytics Dashboard** built on a single table dataset named **InsuranceData**. It contains (detected) key KPIs, slicers, distribution charts and a pivot table to explore policies, claims, and customer demographics.

**File info**

* Filename: `PrismDashboard.pbix`
* Size: 526893 bytes (\~514.9 KB / 0.502 MB)
* PBIX layout version: 1.28
* Created from: Cloud (Release 2025.08)
* Power BI Desktop (detected) version: 2.146.304.0
* Theme: Innovate

## High-level findings (structure)

* Pages: 1 (Page 1)
* Visuals detected: 13
* Primary data source/table referenced: `InsuranceData`
* Main fields used (detected in queries): Active/Inactive, Age Group, ClaimAmount, ClaimNumber, ClaimStatus, CoverageAmount, CustomerID, Gender, PolicyNumber, PolicyType, PremiumAmount

## Visuals summary

| #  | Type         | Fields / Measures                                                        | Position (x,y) | Size (w x h)      |
| -- | ------------ | ------------------------------------------------------------------------ | -------------- | ----------------- |
| 0  | slicer       | InsuranceData.PolicyNumber                                               | (313.4, 18.1)  | (262.0 x 76.6)    |
| 1  | slicer       | InsuranceData.ClaimNumber                                                | (575.4, 18.1)  | (262.0 x 76.6)    |
| 2  | slicer       | InsuranceData.CustomerID                                                 | (837.4, 18.1)  | (262.0 x 76.6)    |
| 3  | textbox      | PRISM INSURANCE PVT. LTD. (title)                                        | (29.2, 18.1)   | (371.9 x 247.9)   |
| 4  | cardVisual   | Sum(InsuranceData.PremiumAmount)                                         | (29.2, 286.0)  | (250.96 x 115.91) |
| 5  | cardVisual   | Sum(InsuranceData.ClaimAmount)                                           | (287.2, 286.0) | (250.96 x 115.91) |
| 6  | multiRowCard | InsuranceData.Gender, CountNonNull(Gender)                               | (545.2, 286.0) | (371.9 x 174.36)  |
| 7  | ribbonChart  | InsuranceData.ClaimStatus, CountNonNull(ClaimStatus)                     | (916.5, 286.0) | (371.9 x 248.94)  |
| 8  | barChart     | InsuranceData.PolicyType, Sum(PremiumAmount)                             | (29.2, 424.0)  | (399.12 x 227.78) |
| 9  | lineChart    | InsuranceData.Age Group, Sum(ClaimAmount)                                | (431.2, 424.0) | (399.12 x 218.71) |
| 10 | cardVisual   | Sum(InsuranceData.CoverageAmount)                                        | (833.5, 286.0) | (250.96 x 115.91) |
| 11 | donutChart   | InsuranceData.Active/Inactive, CountNonNull(Active/Inactive)             | (451.5, 424.0) | (416.25 x 227.78) |
| 12 | pivotTable   | Sum(CoverageAmount), InsuranceData.PolicyType, InsuranceData.ClaimStatus | (835.5, 481.8) | (416.25 x 219.72) |

## Detected measures / aggregations

* Sum(InsuranceData.PremiumAmount)
* Sum(InsuranceData.ClaimAmount)
* Sum(InsuranceData.CoverageAmount)
* CountNonNull(InsuranceData.Gender)
* CountNonNull(InsuranceData.ClaimStatus)
* CountNonNull(InsuranceData.Active/Inactive)

## Text & Branding

* Report title (textbox): **PRISM INSURANCE PVT. LTD.**

## What I could detect / what you created

Based on the PBIX contents (Report/Layout and visual queries), I can confidently say you have created:

* Slicers for `PolicyNumber`, `ClaimNumber`, and `CustomerID` for record-level filtering.
* KPI cards showing aggregated sums (Premium, ClaimAmount, CoverageAmount).
* Visuals for distribution / segmentation: Gender (multi-row card), ClaimStatus (ribbon chart), PolicyType vs Premium (bar), Age Group vs Sum(ClaimAmount) (line chart).
* A donut chart for `Active/Inactive` status.
* A pivot table showing `CoverageAmount` summarized by `PolicyType` and `ClaimStatus`.
* Report-level/layout theme applied (`Innovate` and base theme file referenced).
* Formatting and layout: title textbox at top-left; slicers across the top; KPI cards grouped; charts occupy the middle and lower areas; pivot table at bottom-right.

> **Note on limitations:** the `DataModel` inside a PBIX is a binary tabular model. I could not parse the full tabular schema, row counts, relationships or DAX measure definitions from the binary `DataModel` file using this automated inspection. The visual queries and layout were sufficient to enumerate fields used in visuals and measure aggregations but not to extract custom DAX formulas, calculated columns, or model relationships.

## Suggested next steps / improvements

* Export or provide the dataset (CSV / Excel) or export the Tabular model (from Tabular Editor) if you want a full schema and DAX audit (measures, column types, relationships).
* Add a date/period slicer and a proper 'Date' table (if applicable) to enable time-series analysis.
* Create explicit DAX measures with clear names (e.g., `Total Claims`, `Average Claim`) instead of relying on implicit aggregations — this helps reuse and clarity.
* Add drill-through pages for claim detail, and tooltips for charts.
* Add a small 'Data Dictionary' page or an auxiliary table listing field definitions and units.
* Consider performance: limit high-cardinality slicers and use aggregations or import-mode optimization if dataset is large.
* Add row-level security (RLS) if this dashboard will be shared with users who should not see all records.

## How to open / reproduce

1. Open `PrismDashboard.pbix` in Power BI Desktop (version 2.146.304.0 or later).
2. Publish the PBIX to Power BI Service to share dashboards online (if desired).
3. To inspect measures & model in detail, connect with Tabular Editor or export the model.

## If you want more

I can:

* Attempt to extract DAX measures and relationships if you export the model (Tabular Editor JSON or PBIT).
* Produce a concise `README.md` (this document) as a downloadable file (done).
* Create a one-page summary slide (PowerPoint) with screenshots and top 5 insights (if you provide snapshots or data).
* Generate suggested DAX measures and Power BI best-practice patterns.

---

*Automated analysis performed by parsing `Report/Layout`, `DiagramLayout`, `Settings`, and `Metadata` inside the uploaded PBIX. DataModel (binary) was not parsed.*

<img width="1444" height="814" alt="image" src="https://github.com/user-attachments/assets/616e56f4-e92f-4b40-8771-6f7618882bc0" />
