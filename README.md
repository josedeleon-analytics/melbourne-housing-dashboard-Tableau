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

![Dashboard Preview](plots/dasbhboard.png)

🔗 [View Full Dashboard on Tableau Public](https://public.tableau.com/app/profile/josedeleon-analytics/viz/MelbourneHousingDashboard/Dashboard)  

---

## 🔍 Visualizations  

### 1. Average Price by Property Type  
![Average Price by Property Type](plots/average%20price%20by%20property%20type.png)  

### 2. Price per sqm by Property Type  
![Price per sqm by Property Type](plots/price%20per%20sqm%20by%20property%20type.png)  

### 3. Average Price by Region  
![Average Price by Region](plots/average%20price%20by%20region.png)  

### 4. Price per sqm by Region  
![Price per sqm by Region](plots/price%20per%20sqm%20by%20region.png)  

### 5. Number of Rooms vs Land Size  
![Number of Rooms vs Land Size](plots/number%20of%20rooms%20vs%20land%20size.png)  

### 6. Average Price vs Distance to the Center  
![Average Price vs Distance](plots/average%20price%20vs%20distnace%20to%20the%20center.png)  

### 7. Average Price by Month  
![Average Price by Month](plots/average%20price%20by%20month.png)  


---

## ⏳ Parameter & Calculated Fields  

### 📌 Parameter: Price or Room selection 
- **Price or Room Selection Parameter**  
  This parameter allows users to toggle between three perspectives:  
- **Average Price**  
- **Price per sqm**  
- **Number of Rooms**  
  ![Parameter Setup](plots/parameter.png) 

- **Dynamic Titles (Calculated Fields)**  
  Each visualization title updates dynamically depending on the parameter selection:  
  - Property Type  
  - Region  
  - Land Size  
  - Distance to Center  
  - Month  

### 📌 Calculated Field: Selected Price or Rooms  
This field drives the metric shown across all visualizations, dynamically switching based on the parameter selection.  

```tableau
IF [Price or Room selection] = "Average Price" THEN AVG([Price])
ELSEIF [Price or Room selection] = "Number of Rooms" THEN MEDIAN([Rooms])
ELSEIF [Price or Room selection] = "Price per sqm" THEN
    AVG([Price]) / NULLIF(AVG([Building Area]), 0)
END
```
