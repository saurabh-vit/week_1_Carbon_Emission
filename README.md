# 🌍 Climate & Emissions Data Cleaning Project

This project focuses on cleaning and transforming a complex Excel-based dataset (`Carbon_Emission.xls`) that includes country-level environmental, economic, demographic, and energy-related indicators. The goal is to prepare the data for meaningful analysis and machine learning modeling.

---

## 🎯 Objective

- Analyze how country-specific parameters (e.g., population, GDP, energy use) affect climate indicators like CO₂ emissions and precipitation.
- Restructure the dataset for machine learning by organizing features properly and handling missing or inconsistent data.

---

## 📊 Dataset Features

The dataset includes country-level yearly data on:

- **Greenhouse Gas Emissions**: CO₂, CH₄, N₂O, etc.
- **Demographics**: Population, Urbanization, Growth
- **Economy**: GDP, GNI, FDI
- **Land Use**: Cereal Yield, Protected Areas
- **Climate**: Precipitation, Disasters
- **Energy**: Electricity Access, Energy Use
- **Health**: Mortality Rate, Infrastructure

---

## 🔧 Data Cleaning & Transformation Workflow

### ✅ Steps Performed:

1. **Load Excel File**  
   - Read using `pandas.ExcelFile` and extract the `Data` sheet.

2. **Initial Cleaning**  
   - Removed rows where `'SCALE'` or `'Decimals'` is `'Text'`
   - Dropped columns: `'Country name'`, `'Series code'`, `'SCALE'`, `'Decimals'`

3. **Handle Missing Data**  
   - Replaced `'..'`, empty strings, and `'N/A'` with `NaN`
   - Converted all year columns to numeric

4. **Feature Renaming**  
   - Simplified verbose names in `'Series name'` to short labels (e.g., `CO2 emissions, total` → `co2_ttl`)

5. **Data Reshaping**  
   - Used `pd.melt()` to transform each feature into a long format (`country`, `year`, `value`)
   - Merged all features into a single dataset using `reduce()` on `country` and `year`

6. **Missing Value Analysis & Filtering**  
   - Filtered out years and countries with excessive missing values
   - Dropped columns with more than 20 missing values
   - Removed rows with any remaining NaN

7. **Export Final Dataset**  
   - Final clean dataset exported as `data_cleaned.csv`

---

## 📁 Output

- **Cleaned Dataset**: `data_cleaned.csv`  
  Ready for modeling or further EDA.

---

## 🛠 Tech Stack

- **Language**: Python 3.11+
- **Libraries**:  
  - `pandas`  
  - `numpy`  
  - `matplotlib`  
  - `seaborn`

---

## 📌 How to Use

```bash
# Install dependencies
pip install pandas numpy matplotlib seaborn

# Run the script
python clean_data.py

# Output file
data_cleaned.csv
