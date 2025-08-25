# 🏠 Tableau Dashboard Project: Melbourne Housing Market  

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg) 
![Last Commit](https://img.shields.io/github/last-commit/josedeleon-analytics/tableau-melbourne-housing) 
![Tableau](https://img.shields.io/badge/Tableau-Dashboards-blue?logo=tableau&logoColor=white)

**Prepared by:** Jose De Leon  
**Date:** June 27, 2025  

---

## 📊 Project Overview  
This project explores the **Melbourne housing market** through an interactive Tableau dashboard built on 20,993 property sales records. The dashboard provides insights into housing prices, property characteristics, and market dynamics using parameter-driven storytelling and interactive filters.  

Key features include:  
- Five dynamic visualizations (bar, histogram, line, and stacked plots).  
- A parameter that toggles between **Average Price, Price per sqm, and Number of Rooms**.  
- Interactive filters for **Region, Property Type, Rooms, Land Size, Distance, and Time**.  
- A unified dashboard displaying all visualizations for holistic analysis.  

This project demonstrates strong capabilities in **Tableau, parameter-driven analysis, and real estate market insights**.  

---

## 📂 Project Files  
- [`Dashboard - Melbourne Housing`](Dashboard%20-%20Melbourne%20Housing%20-%20github.twbx)  
- [`Dataset`](melbourne_housing_cleaned.csv)  
- [`Plots`](plots/)  
- [`Project Tableau Dashboard PDF`](Project%20Tableau%20Dashboard%20Melbourne.pdf)  
- [`LICENSE`](LICENSE)  
- [`README.md`](README.md)  

---

## 📸 Dashboard Demonstration  

[![Dashboard Preview](plots/final_dashboard.png)](https://public.tableau.com/app/profile/josedeleon-analytics/viz/MelbourneHousingDashboard/Dashboard)  

🔗 [View Full Dashboard on Tableau Public](https://public.tableau.com/app/profile/josedeleon-analytics/viz/MelbourneHousingDashboard/Dashboard)  

---

## 🔍 Visualizations  

### 1. Average Price by Property Type  
Filters: Region, Rooms, Year Built, Land Size, Date  
![Average Price by Property Type](plots/avg_price_property_type.png)  

### 2. Price per sqm by Property Type  
Filters: Region, Rooms, Year Built, Land Size, Date  
![Price per sqm by Property Type](plots/price_per_sqm_property_type.png)  

### 3. Average Price by Region  
Filters: Region, Rooms, Year Built, Land Size, Date  
![Average Price by Region](plots/avg_price_region.png)  

### 4. Price per sqm by Region  
Filters: Region, Rooms, Year Built, Land Size, Date  
![Price per sqm by Region](plots/price_per_sqm_region.png)  

### 5. Number of Rooms vs Land Size  
Filters: Region, Rooms, Year Built, Type  
![Rooms vs Land Size](plots/rooms_vs_landsize.png)  

### 6. Average Price vs Distance to the Center  
Filters: Region, Rooms, Year Built, Land Size  
![Average Price vs Distance](plots/avg_price_distance.png)  

### 7. Average Price by Month  
Filters: Region, Rooms, Year Built, Type  
![Average Price by Month](plots/avg_price_month.png)  

### 8. Final Dashboard – Melbourne Housing Insights  
![Final Dashboard](plots/final_dashboard.png)  

---

## ⏳ Parameter & Calculated Fields  

- **Price or Room Selection Parameter**  
  This parameter allows users to toggle between three perspectives:  
- **Average Price**  
- **Price per sqm**  
- **Number of Rooms**  
  ![Parameter](plots/parameter.png)  

- **Dynamic Titles (Calculated Fields)**  
  Each visualization title updates dynamically depending on the parameter selection:  
  - Property Type  
  - Region  
  - Land Size  
  - Distance to Center  
  - Month  

Example of calculated field:  
```tableau
IF [Parameter Price or Room] = "Average Price" THEN AVG([Price])
ELSEIF [Parameter Price or Room] = "Price per sqm" THEN SUM([Price])/SUM([BuildingArea])
ELSEIF [Parameter Price or Room] = "Number of Rooms" THEN AVG([Rooms])
END
