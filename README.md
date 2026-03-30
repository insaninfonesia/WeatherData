# WeatherData
Weather Data Set from Colabs Project

<b>Dataset Description</b>

<b>Weather Data</b> is a collection of environmental condition records gathered from a monitoring point located in Balai Silvofishery Maros Regency, South Sulawesi Province and Pulo Aceh, Aceh Besar Regency, Aceh Province. The dataset includes key weather parameters such as temperature, humidity, rainfall, light intensity, wind speed, and other atmospheric indicators. This dataset helps researcher observe daily weather changes, analyze local climate patterns, and support research, planning, or environmental modeling in the area.

The data collected from Pulo Aceh is incomplete due to limitations in data transmission, such as frequent power outages and very limited internet access. Environmental conditions in Indonesia’s outermost regions present unique challenges for the transmission and reception of data from installed sensors. Additionally, sensors located in open sea areas face further difficulties, including natural interference (such as sea vapor and high salinity) as well as disturbances from marine life.

<b>Key Considerations Prior to Implementing AI/ML Models</b>
1. Data Quality and Completeness (Primary Concern)
Data quality represents the most critical factor in determining the effectiveness of any AI/ML implementation. Several key issues have been identified:
- Low variability in data
Observations indicate that temperature remains constant at 27.7°C, humidity is consistently around ~80%, while pressure and wind speed values are entirely absent. Models trained on such homogeneous data tend to learn trivial patterns (e.g., constant predictions), rendering them ineffective for meaningful anomaly detection.
- High proportion of missing values
Significant gaps are present in key variables, including Pressure, Wind Speed, Device Status (frequently labeled as “unknown”), and Battery levels (consistently reported as 0%). This indicates incomplete sensor reporting and poses a major limitation, as machine learning models require sufficiently complete feature sets to perform reliably.
- Irregular data intervals
The Recent Measurements dataset shows inconsistent timestamps (e.g., second 42, 47, 48, 49, 49, 50), suggesting non-uniform sampling intervals. This inconsistency complicates the application of time-series models, which typically assume fixed and regular observation intervals.

2. Data Limitations That Must Be Considered
(Implicitly reflected in the issues above: lack of variation, missing data, and short observation period.)

3. What Can and Cannot Be Done with the Current Data
What is feasible with the current dataset:
- Simple anomaly detection on humidity (as it shows more variation than temperature) 
- Cross-site comparison for outlier detection
- Alerts when values fall outside historical ranges

What cannot yet be done reliably:
- Weather prediction — requires non-null pressure and wind speed data
- Flood or extreme weather detection — requires historical extreme event data
- Accurate per-site models — data is too homogeneous and covers too short a time span

Priority Recommendations Before Further AI Investment
1. Fix the hardware first — Ensure all sensors consistently report at least four key parameters: temperature, humidity, pressure, and wind speed. Poor data will inevitably produce poor models.
2. Collect at least one full year of historical data — This allows models to learn seasonal patterns. The system has only been active since August 2025, meaning there are currently about 7 months of data, which is insufficient to capture a full seasonal cycle.
3. Implement data quality scoring before modeling — Flag records with low battery, unknown device status, or null values as “low confidence,” so the model is not trained on unreliable data.
4. Start with simple models — Use threshold-based methods and moving averages before jumping into complex approaches like deep learning. With the current dataset, complex models are more likely to overfit than to provide meaningful insights.

<b>Licensing Information</b>

The dataset is released under the terms of CC-BY-SA 4.0. By using this dataset, you are also bound to the respective Terms of Use and License of the dataset. For commercial use in small businesses and startups, please contact us (infonesiainsan@gmail.com) for permission to use the datasets by informing company profile and propose of usage.

<b>Acknowledgement</b>

This research work is funded and supported by The Deutsche Gesellschaft für Internationale Zusammenarbeit (GIZ) GmbH and FAIR Forward - Artificial Intelligence for all. We thank Common Room Network Foundation for providing the resources for this project.

<b>Contact Us</b>

If you have any question please contact our support team at infonesiainsan@gmail.com
