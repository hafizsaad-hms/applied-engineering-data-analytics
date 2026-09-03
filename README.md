# applied-engineering-data-analytics
Automated QA pipelines, dimensional metrology analysis, and statistical feature preprocessing using Python, NumPy, Pandas, and Scikit-Learn
# Applied Engineering Data Analytics & Quality Control Framework

A comprehensive Python framework covering mechanical engineering quality assurance, automated dimensional metrology, data wrangling, feature engineering, and interactive visualization. 

This repository documents hands-on laboratory implementations bridging mechanical testing protocols with modern data science pipelines.

> **Note:** The complete laboratory notebook and execution logs are available in the repository root: [`2024-ME-304-ICPDS.pdf`](./2024-ME-304-ICPDS.pdf).

---

## 🛠️ Tech Stack & Libraries

- **Language:** Python 3.10+
- **Numerical Computing & Metrology:** NumPy
- **Data Engineering & Manipulation:** Pandas, OpenPyXL
- **Machine Learning Preprocessing:** Scikit-Learn
- **Exploratory Data Analysis & Plotting:** Matplotlib, Seaborn
- **Interactive Dashboards:** Plotly Express
- **API Data Integration:** Wbdata (World Bank API)

---

## 📋 Laboratory Modules & Implementation Details

### Lab 01: Tensile Strength Inspection Automation
- **Focus:** Basic conditional automation and batch testing.
- **Implementation:** Evaluates tensile strength measurements across specimen batches against a structural threshold of $\ge 250\text{ MPa}$.
- **Output:** Classifies rods as *Pass* or *Fail* and aggregates total acceptance/rejection metrics for quality verification.

### Lab 02: Shaft Diameter Tolerance Verification
- **Focus:** Range-bound dimensional inspection.
- **Implementation:** Implements bilateral tolerance boundaries ($49 < \text{diameter} \le 51\text{ mm}$) to verify precision-machined shafts.
- **Output:** Classifies components into *Within Tolerance* or *Out of Tolerance* categories with a final inspection report.

### Lab 03: Brinell Hardness Testing Automation
- **Focus:** Modular functions and boolean return validation.
- **Implementation:** Custom validation function `check_hardness(value)` testing whether specimen hardness falls within $150 \le \text{HB} \le 200$.
- **Output:** Batch evaluation of 8 manufactured components with pass/fail summary metrics.

### Lab 04: Vectorized Dimensional Metrology with NumPy
- **Focus:** High-performance vectorized array processing and statistical metrics.
- **Implementation:** 
  - Ingests raw continuous diameter readings into 1D NumPy arrays.
  - Applies boolean mask logic (`(data >= 49) & (data <= 51)`) to detect tolerance compliance without explicit loops.
  - Extracts exact index locations of defective parts via `np.where(~tolerance_mask)`.
- **Output:** Generates statistical distributions: sample mean, sample standard deviation ($ddof=1$), minimum, and maximum shaft dimensions.

### Lab 05: Data Wrangling & Tabular Cleansing with Pandas
- **Focus:** Production tabular data cleaning and ETL pipeline.
- **Implementation:**
  - Automated missing data removal via `dropna()`.
  - Feature engineering: calculated dynamic metric `tip_percentage = (tip / total_bill) * 100`.
  - Conditional row filtering for high-value records (`total_bill > 20`).
  - Serialized cleaned data directly to Excel format (`tips_cleaned.xlsx`) via OpenPyXL.

### Lab 06: Exploratory Data Analysis & Statistical Plotting
- **Focus:** Univariate and multivariate distribution analysis using Matplotlib and Seaborn.
- **Visualizations Implemented:**
  - **Line Chart:** Sepal length distribution trends across index series.
  - **Scatter Plot:** Sepal length vs. petal length segmented by plant species.
  - **Boxplot:** Interquartile ranges and outlier detection for total bill by day.
  - **Histogram:** Frequency distribution of bill magnitudes (10-bin resolution).
  - **Pie Chart & Bar Chart:** Categorical volume breakdown and average bill calculations with confidence intervals.

### Lab 07: Feature Encoding for Predictive Modeling
- **Focus:** Categorical preprocessing using Scikit-Learn.
- **Techniques Implemented:**
  - **Label Encoding:** Binary conversion for binary categorical features (`Gender`).
  - **One-Hot Encoding:** Binary column decomposition (`pd.get_dummies`) for nominal geographic locations (`City`).
  - **Ordinal Encoding:** Structured rank preservation (`OrdinalEncoder`) across academic qualifications (`Matric` $\rightarrow$ `Intermediate` $\rightarrow$ `Bachelor` $\rightarrow$ `Master`).

### Lab 08: Feature Scaling & Distribution Normalization
- **Focus:** Numerical transformations for algorithm convergence using Scikit-Learn.
- **Techniques Compared:**
  - **Min-Max Scaling (`MinMaxScaler`):** Bounds bounded features into a $[0, 1]$ interval.
  - **Standardization (`StandardScaler`):** Centers data around zero mean with unit standard deviation ($Z\text{-score}$).
  - **Robust Scaling (`RobustScaler`):** Uses median and Interquartile Range (IQR) to normalize features resiliently against extreme outliers.

### Lab 09: Interactive Exploratory Dashboards with Plotly
- **Focus:** Browser-based interactive analytical visualizations.
- **Visualizations Implemented:**
  - Multi-variable scatter bubble charts (mapping GDP vs. Life Expectancy, bubble size weighted by population).
  - Categorical interactive bar charts and GDP growth line charts with active hover data.
  - Country-level population distribution pie charts.

### Lab 10: Macroeconomic Demographic Time-Series Ingestion
- **Focus:** External REST API queries and time-series visualization.
- **Implementation:**
  - Connected to the World Bank Data API (`wbdata`) to extract historical population series (`SP.POP.TOTL`) from 1960 to the present.
  - Cleaned and sorted chronological timestamps.
  - Plotted multi-national demographic growth trajectories comparing Pakistan and the United States using Matplotlib.

---

## 🎯 Engineering Competencies Demonstrated

- **Quality Assurance Automation:** Translating mechanical tolerance and strength thresholds into automated software checks.
- **Vectorized Array Metrology:** Eliminating iterative performance bottlenecks in measurement datasets using NumPy masks.
- **Data Engineering:** Building reproducible cleaning, transformation, and serialization routines in Pandas.
- **Feature Pipeline Design:** Preparing mixed (numerical and categorical) data arrays for machine learning ingestion.
