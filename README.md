# Industry Lab-Project Folder Structure

The Industry Lab-Project folder is organized as follows:

## Data
- **Original**: Contains the original data from FCA.
- **Processed**: Contains data processed from the original or derived datasets.
- **Reference**: Data representing average curves and control bands.

## Models
- Contains saved machine learning models.

## Script
- **Part0- Data Extraction.ipynb**: Extracts useful data from the original JSON files.
  - Input: Original data
  - Output: `full_rows_df.pkl`

- **Part1- Data Preparation.ipynb**: Filters out irrelevant or anomalous data and extracts a test observation for deployment.
  - Input: `full_rows_df.pkl`
  - Output: 
    - `clean_rows_df.pkl`
    - `test_value.pkl`

- **Part2- Statistical Anomaly Detection.ipynb**: Develops the statistical algorithm.
  - Input: `clean_rows_df.pkl`
  - Output: 
    - `reference_volt_lag_curves.pkl`
    - `reference_volt_curves.pkl`
    - `reference_current_curves.pkl`
    - `with_stat_anomalies.pkl`

- **Part3.a- Machine Learning_voltage.ipynb**: Processes and develops the machine learning model for voltage.
  - Input: `clean_rows_df.pkl`
  - Output: 
    - `ML_voltage_with_anomalies.pkl`
    - `iForest_volt.pkl`

- **Part3.b- Machine Learning_current.ipynb**: Processes and develops the machine learning model for current.
  - Input: `clean_rows_df.pkl`
  - Output: 
    - `ML_current_with_anomalies.pkl`
    - `iForest_curr.pkl`

- **Part4- Anomaly Analysis.ipynb**:
  - Input: 
    - `reference_volt_curves.pkl`
    - `reference_current_curves.pkl`
    - `with_stat_anomalies.pkl`
    - `ML_voltage_with_anomalies.pkl`
    - `ML_current_with_anomalies.pkl`

- **Part5- Deploy.ipynb**:
  - Input: 
    - `iForest_volt.pkl`
    - `iForest_curr.pkl`
