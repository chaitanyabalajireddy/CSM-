
# Power Demand Forecasting with Integrated Weather Data

#### **1. Introduction**
This study explores the integration of weather data into power demand forecasting to improve energy management. Key objectives include:
- **Optimizing energy generation and grid stability** through better demand prediction.
- **Integrating renewables** by analyzing weather-driven impacts on demand and supply.  
**Key Factors:** Temperature, solar radiation, and wind speed influence both energy demand (heating/cooling needs) and renewable generation.

---

#### **2. Data Preparation**
- **Data Sources:** Power demand data (actual and forecasted) and weather data (temperature, solar radiation, wind speed) from multiple regions.
- **Preprocessing Steps:**
  1. **Handling Missing Data:** Imputed using median/forward-fill methods.
  2. **Data Merging:** Aligned power demand with weather data via timestamps.
  3. **Normalization:** Scaled features for consistency.
  4. **Feature Engineering:** Added lag features, rolling averages, and seasonal trends.
  5. **Data Split:** Divided into training (early period) and testing sets.

---

#### **3. Exploratory Data Analysis (EDA)**
- **Weather Trends:** Seasonal and regional temperature/radiation patterns analyzed across six countries: FR, DE, ES, IT, NL, and PL.
- **Correlation Insights (Netherlands):**
  - **Load vs. Temperature:** Moderate negative correlation (-0.40) indicates reduced heating demand during warmer periods.
  - **Solar vs. Radiation:** Strong positive correlation with direct radiation (0.57).
  - **Wind Generation:** Offshore and onshore wind highly correlated (0.92), less influenced by weather variability.

---

#### **4. Temperature Trends Across Countries**
- **France (FR):** Hot summers, cold winters.
- **Germany (DE):** Moderate seasonal variation.
- **Spain (ES) & Italy (IT):** Hot summers, mild winters (Mediterranean climate).
- **Netherlands (NL):** Minimal variation (oceanic climate).
- **Poland (PL):** Distinct seasonal contrasts (continental climate).  

---

#### **5. Corelation Analysis**
![image](https://github.com/user-attachments/assets/f4e45a0e-11e6-4f4f-a96c-65146e7c702c)
![image](https://github.com/user-attachments/assets/dd83b15f-333c-4113-864b-0283e10be63d)
![image](https://github.com/user-attachments/assets/de88c676-b011-4899-bea9-63cfbdd5b142)
![image](https://github.com/user-attachments/assets/ea0f0f86-163f-4858-8f0e-b4909dc330eb)
![image](https://github.com/user-attachments/assets/9eed7008-ad35-48ef-a241-1445b1a20587)


### Base Models RMSE:
| Model           | France (FR) | Germany (DE) | Spain (ES) | Italy (IT) | Netherlands (NL) | Poland (PL) |
|------------------|-------------|--------------|------------|------------|-------------------|-------------|
| **ARIMA**       | 5388.15     | 6138.56      | 2694.98    | 4876.16    | 1081.08           | 1967.74     |
| **Random Forest**| 696.21      | 1542.46      | 295.43     | 662.17     | 438.50            | 285.83      |
| **XGBoost**     | 678.45      | 1564.06      | 287.64     | 654.30     | 440.21            | 290.62      |
| **LSTM**        | 678.45      | 1564.06      | 287.64     | 654.30     | 440.21            | 290.62      |

Weights were calculated for each model based on the inverse RMSE, and these weights were used for ensemble forecasting.

---

## Results and Visualizations
The following visualizations showcase actual vs. predicted power demand for each country using the ensemble model:

![image](https://github.com/user-attachments/assets/33afe21d-b5d4-4429-996f-85c8c5ea8ca9)


The hybrid ensemble model accurately captures daily and seasonal trends across all six countries.

---

## Datasets
The project requires:
- **Historical Power Demand Data**: Hourly/Daily consumption for FR, DE, ES, IT, NL, and PL.
- **Weather Data**: Temperature, humidity, wind speed, etc., for corresponding regions.

Ensure the dataset files are formatted in `.csv` and stored in the `data/` directory.

---
### **Contributions**

- **M Batul Abbas** (SE23MAID010): Contributed to **code development** for implementing ARIMAX and machine learning models like Random Forest AND Ensemble model.  
- **K Chaitanya Balaji Reddy** (SE23MAID007): Handled **project management, documentation, and analysis**, contributing to the integration and evaluation of all models, including Hybrid Models.  
- **Suman Tiwari** (SE23MAID019): Contributed to **code development**, working on deep learning model like LSTM , and integrating them into the forecasting pipeline.  
- **A Akhil Sai** (SE23MAID001): Contributed to model development and implementation.  
- **K Sumedha Reddy** (SE23MAID018): Contributed to data preparation and model training.

---

