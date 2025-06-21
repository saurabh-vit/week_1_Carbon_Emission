# Week_1_Carbon_Emission

🌍 Climate & Emissions Data Cleaning Project
This Python project focuses on cleaning and restructuring a complex country-level climate and emissions dataset (Carbon_Emission.xls) to prepare it for further analysis and machine learning modeling.

🔍 Objective
To analyze the relationship between country-specific features—such as greenhouse gas emissions, demographics, land use, economic indicators, and health infrastructure—and their impact on climate indicators like CO₂ emissions and precipitation.

📊 Dataset Overview
The dataset includes:

Greenhouse Gases: CO₂, CH₄, N₂O, and others

Demographics: Population, Urban growth

Economy: GDP, GNI, FDI

Land Use: Cereal yield, Protected areas

Climate: Precipitation, Disasters

Energy & Health: Electricity access, Mortality rates

🧹 Data Cleaning & Transformation Steps
Load and Preview Data

Load Excel file using pandas.

Preview structure, column names, and data types.

Remove Irrelevant Entries

Drop rows where 'SCALE' or 'Decimals' is 'Text'.

Remove unused columns: 'SCALE', 'Series code', 'Country name'.

Handle Missing Values

Replace '..', empty strings, and 'N/A' with NaN.

Convert year columns to numeric types.

Rename Features

Simplify Series name values into readable short feature names using a dictionary.

Restructure Data

Use pd.melt() to reshape data into a long format with ['country', 'year', feature].

Merge Features

Combine all variables into a single DataFrame with country-year as keys.

Missing Value Analysis & Filtering

Remove years and countries with too many missing values.

Drop columns with excessive missing values.

Final cleanup with dropna() to ensure a complete dataset.

Export Cleaned Dataset

Export the final cleaned dataset to data_cleaned.csv for downstream ML use.

🛠️ Technologies Used
Python 3.11+

Pandas

NumPy

Matplotlib / Seaborn (for visualizations)

📁 Output
Final clean dataset: data_cleaned.csv

Ready for modeling and exploratory data analysis (EDA)
