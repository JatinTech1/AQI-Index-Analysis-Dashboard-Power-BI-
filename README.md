# AQI Index Analysis Dashboard (Power BI)

An interactive Power BI dashboard that analyzes **Air Quality Index (AQI)** across India with dynamic filters, geographic visualization, pollutant insights, and trend analysis. This project demonstrates data modeling, DAX measures, and effective dashboard design for environmental analytics.

---

## Key Features

* **Dynamic KPIs**: Current AQI, Max AQI, Primary Pollutant, and AQI Category
* **Geospatial Analysis**: AQI distribution across states using **Azure Maps**
* **Area Comparison**: Top cities/areas ranked by average AQI
* **AQI Level Distribution**: Donut chart showing category-wise split
* **Pollutant Occurrence Frequency**: PM2.5, PM10, O3, NO2, CO, etc.
* **Time Trends**: Monthly AQI trend line
* **Slicers**: Year, State, City, Month for interactive filtering

---

## Tools & Technologies

* **Power BI Desktop**
* **DAX (Data Analysis Expressions)**
* **Power Query (ETL)**
* **Azure Maps Visual**
* **Microsoft Excel / CSV (Data Source)**

---

## Dashboard Overview

The dashboard is designed with a dark theme for clarity and includes:

* **Gauge KPI** for overall AQI (e.g., Delhi: 208)
* **Bar Chart** for average AQI by area
* **Map Visual** for state-wise AQI intensity
* **Donut Chart** for AQI category distribution
* **Horizontal Bar Chart** for pollutant frequency
* **Line Chart** for monthly AQI trend

---

## Data Description

The dataset contains air quality readings with the following key fields:

* `State`
* `City`
* `Area`
* `Date`
* `Year`, `Month`
* `AQI`
* `AQI Category`
* `PM2.5`, `PM10`, `O3`, `NO2`, `CO` (Pollutants)

> **Note:** Data is cleaned and transformed using Power Query before modeling.

---

## Important DAX Measures

```DAX
Total Records = COUNTROWS('AQI_Data')

Average AQI = AVERAGE('AQI_Data'[AQI])

Max AQI = MAX('AQI_Data'[AQI])

Primary Pollutant =
VAR MaxPollutant =
    MAXX(
        {
            ("PM2.5", AVERAGE('AQI_Data'[PM2.5])),
            ("PM10", AVERAGE('AQI_Data'[PM10])),
            ("O3", AVERAGE('AQI_Data'[O3])),
            ("NO2", AVERAGE('AQI_Data'[NO2])),
            ("CO", AVERAGE('AQI_Data'[CO]))
        },
        [Value]
    )
RETURN MaxPollutant
```
## Use Cases

* Environmental analysis
* Urban air quality monitoring
* Data Analyst / Power BI portfolio project
* Interview showcase project

---

## Highlights

* Built an interactive **AQI Analysis Dashboard** using Power BI to visualize air quality trends across Indian states.
* Implemented **DAX measures** and **Power Query transformations** to calculate KPIs and pollutant insights.
* Integrated **Azure Maps** for geospatial analysis and designed an intuitive UI with slicers and KPIs.

<img width="1225" height="688" alt="Screenshot 2026-01-14 040535" src="https://github.com/user-attachments/assets/1d3944a6-542f-4b24-8a6d-c9b747f0dbae" />


