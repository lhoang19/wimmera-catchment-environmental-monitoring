# Wimmera Catchment Environmental & Water Security Dashboard

An interactive Tableau dashboard designed to monitor water quality thresholds, assess ecological risk profiles, and protect water security across the Wimmera catchment in Victoria, Australia.

## 📊 Project Overview
The Wimmera region covers approximately 10% of Victoria (2.3 million hectares) and represents a vital economic and ecological powerhouse. While the landscape is dominated by a lucrative $691 million broadacre cropping industry, its waterways serve as critical oases in a relatively dry environment. This project centralizes historical water quality data to track environmental guideline compliance and empower stakeholders to make proactive, data-driven decisions.


## 🏛️ Executive Summary

### Strategic Context
The Wimmera is Victoria's fifth-largest catchment management region, where 53% of the land (1.2 million hectares) is dedicated to broadacre farming. The region supports a significant irrigation and grazing industry backed by valuable groundwater resources, and holds 25% of Victoria's wetlands. This includes the Barringgi Gadyin (Wimmera River), the state’s largest inland-terminating river, which feeds the freshwater wetland Gurru (Lake Hindmarsh) and the Ramsar-listed Ngalpakatia/Ngelpagutya (Lake Albacutya) system.

### The Business Problem
The intersection of intensive broadacre farming, expanding property sizes (median 765 hectares), and heavy reliance on groundwater creates a severe resource management conflict in a drying climate. Runoff and altered flow regimes threaten critical ecological assets. Managing water quality across distributed stations is currently hindered by fragmented data, making it difficult for catchment authorities to balance agricultural water demands with conservation efforts, or to rapidly identify localized crises like severe salinity spikes and catastrophic anoxic events.

### Dashboard Objective
This interactive dashboard centralizes historical water quality data to track critical environmental guideline thresholds (Dissolved Oxygen < 80\%, Salinity > 1,500$ µS/cm, Temperature > 25 degree Celcius, and $pH \notin [6.5, 8.5]$). By delivering a single, cohesive view of risk profiles and parameter exceedance rates across key water stations, this tool empowers catchment managers, environmental engineers, and agricultural stakeholders to optimise water allocations, safeguard Ramsar wetlands, and protect the region’s $691 million agricultural economy.


## 🛠️ Technical Workflow & Implementation

### 1. Data Cleaning and Standardisation
Raw environmental telemetry data was extracted from the Australian Government's Data about Wimmera CMA (https://data.gov.au/data/dataset/wimmera-cma-water-run) and further consolidated. The data cleaning pipeline implemented in Excel and standardized for Tableau included:
* **Handling Temporal Latency:** Standardized date formats and aggregated daily sensor inputs into consistent annualized and seasonal baselines (2010–2025/2026).
* **Unit Standardization:** Normalized electrical conductivity measurements to microSiemens per centimeter (µS/cm) to map salinity accurately against the $1,500$ µS/cm regulatory threshold.
* **Outlier & Null Handling:** Filtered out system anomalies while retaining critical environmental spikes (e.g., historical extreme hyper-salinity peaks and zero-oxygen hypoxic crashes) to maintain data integrity. For this, Power Query in Excel was utilised to clean up null and empty values

  <img width="1851" height="814" alt="image" src="https://github.com/user-attachments/assets/9b05a427-2aa5-4fd3-bea1-0911b8880e70" />

Raw Data from the Australian Government's Data website



  <img width="1083" height="777" alt="image" src="https://github.com/user-attachments/assets/2404b93a-dadb-43d1-936d-bddae87cead1" />


Cleaned and Standardised Data after using Power Query in Excel 



### 2. Dashboard Prototyping using Generative AI (Claude 
To optimise the user interface (UI) and user experience (UX) before production layout, Generative AI was leveraged as a design collaborator:

<img width="1877" height="773" alt="image" src="https://github.com/user-attachments/assets/a1c28f48-a5ba-4e74-92b8-065a41048562" />

Prototyped Dashboard

The dark-theme interactive user interface presented in this repository serves as a high-fidelity production prototype. To streamline the visual design workflow, Generative AI was leveraged solely as a UI/UX layout collaborator to wireframe container positioning, grid spacing, and dark-mode aesthetic balancing.

All underlying data mechanics—including the core water quality threshold business logic, standardisation of raw telemetry records, parameter aggregation, and key metric tracking—were executed independently through standard data cleaning and visualization workflows.

Based on the Prototyped Dashboard, it helped me suggest key metrics and insights of the water quality management, thus enhancing the effectiveness of environmental management activities within the Wimmera Catchment 

### 3. Tableau Dashboard Build Up
The production dashboard was built using Tableau Desktop utilizing advanced data visualisation mechanics:
First, I built up the 

<img width="488" height="286" alt="image" src="https://github.com/user-attachments/assets/2ceb598d-2a1a-4fde-b915-a8036f39d873" />

Data Architecture on Tableau Public

This diagram illustrates the logical pipeline for the Wimmera environmental dataset.

1. Exceedance_Analysis: Calculated the frequency of breaches against Australian freshwater guidelines (DO, Salinity, pH, Temperature). This powers the "High Risk" and "Critical" alerting system.

2. Seasonal_Summary: Aggregated telemetry into seasonal cohorts to isolate cyclical patterns (e.g., Summer salinity concentration vs. Winter flushing).

3. Yearly_Trend: Visualised longitudinal data (2010–2025) to map the impact of multi-year drought and flooding cycles on catchment health.

Next, I built up interactive dashboards showcasing water quality parameter (Dissolved Oxygen, Salinity, Temperature, and pH Level) across four water stations: Concongella Creek, Glenlofty Creek, Heiffer Station Creek, and Wimmera River within the Wimmwea Catchment.

<img width="1707" height="890" alt="image" src="https://github.com/user-attachments/assets/1d2bfefc-f6e9-4a65-8cd4-8d61fe440447" />


Executive Seasonal Water Parameter across four water stations at Wimmera Catchment Area

<img width="1687" height="891" alt="image" src="https://github.com/user-attachments/assets/cedc9333-77fc-4ce4-9b82-7f7af0147f0c" />

Yearly Parameter Trend from 2010 to 2025 about the behaviour and deviations of DO, Salinity, Temperature and pH Level

<img width="1658" height="870" alt="image" src="https://github.com/user-attachments/assets/97e887fc-ab64-432d-8214-0cdd12550607" />

Parameter Threshold Exceedance and Risk Profile Across four stations within the Wimmera Catchment 

For full detailed stories and dashboard, kindly visit my dashboard on my Tableau Public Profile: https://public.tableau.com/app/profile/lam.hoang2070/viz/WimmeraCatchmentEnvironmentalMonitoring/WimmeraCatchmentEnvironmentalMonitoringReport


---

## 🔍 Key Environmental Insights & Findings

* **Critical:** Concongella Creek recorded DO as low as 14.4% in Autumn and 19.5% in Summer — levels incompatible with most aquatic fauna. Heiffer Station Creek averaged only 39.4% in Autumn. Both sites required urgent dissolved oxygen intervention. All four waterbodies consistently exceed the freshwater EC guideline of 1,500 µS/cm. Concongella Creek (avg 4,730 µS/cm) and Heiffer Station Creek (avg 4,430 µS/cm) exceed the guideline in over 90% of all observations, indicative of dryland salinity mobilisation.
* **Warning:** Wimmera River reaches a mean Summer temperature of 22.3°C, with recorded maxima of 28.9°C. Temperature spikes above 25°C are documented in 3% of River observations, posing thermal stress risk to cold-water fish species, particularly during low-flow years. Heiffer Station Creek recorded mean annual EC of 14,386 µS/cm in 2018 — over 9× the threshold. A renewed spike to 10,400 µS/cm in early 2025 suggests saline groundwater intrusion events linked to drought conditions may be recurring.
* **Observations:** Dissolved oxygen is consistently highest in Winter across all sites (cold water holds more oxygen), and lowest in Autumn–Summer. This pattern confirms that thermal stratification and elevated microbial decomposition are the primary DO depletion mechanisms. pH levels are relatively stable across sites (mean 7.0–7.6), remaining broadly within the 6.5–8.5 guideline range. However, Concongella Creek records pH exceedances in 6.5% of observations, and extreme outliers (pH 13.8) in Heiffer Station Creek warrant instrument calibration review.


---

## 💡 Recommendations for Environmental Management Action

Based on the assessment, here are the strategic management actions I would suggest:

| Priority | Strategy | Recommendation |
| :--- | :--- | :--- |
| **Immediate** | **Emergency Response** | Deploy emergency aerators at Concongella Creek; undertake saline groundwater interception at Heiffer Station Creek. |
| **Short-Term** | **Flow Management** | Establish riparian buffer zones at Glenlofty Creek; develop a salinity management plan for the Wimmera River. |
| **Medium-Term** | **Habitat Restoration** | Plant native vegetation corridors (min. 20m) across all sites to reduce solar exposure and stabilize banks. |
| **Long-Term** | **Systemic Monitoring** | Install automated, continuous water quality sensors integrated with a real-time alerting dashboard. |

## References
1. https://data.gov.au/data/dataset/wimmera-cma-water-run
2. Wimmera Regional Catchment Strategy: 2021 - 2027


```
