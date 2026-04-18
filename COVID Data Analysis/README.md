# COVID-19 Data Analysis (Experiment 19 and 20)

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** A3  
**Date:** 15/04/2026  

---

## 1. Introduction

The COVID-19 pandemic presented an unprecedented global health crisis, generating massive amounts of data as countries tracked the spread of the SARS-CoV-2 virus. This project details the methodology, technical execution, and findings of Experiments 19 and 20, which focus on analyzing this data to understand the global and regional impacts of the virus.

The dataset used, `covid_19_data.csv`, chronicles the daily case counts from the initial outbreak in January 2020 through the end of May 2021. The primary objective of this project is two-fold:

* **Global Macro-Analysis (Experiment 19):** To assess the worldwide distribution of the virus and identify the most severely affected nations.
* **Regional Micro-Analysis (Experiment 20):** To isolate and analyze the pandemic's progression specifically within India, mapping the burden on individual states and union territories.

### Tools and Technologies Used
* **Python:** The core programming language for data manipulation.
* **Pandas & NumPy:** Utilized for data loading, cleaning, feature engineering, and statistical aggregation.
* **Plotly Express:** Employed for generating interactive, high-fidelity geospatial visualizations (choropleth maps).
* **GeoJSON:** Used to map geographical boundaries for regional state-level plotting in India.

---

## 2. Methodology and Data Preprocessing

Real-world datasets are rarely ready for immediate analysis. Before generating insights, a rigorous data cleaning and preprocessing pipeline was implemented to ensure accuracy.

* **Dimensionality Reduction:** The dataset initially contained 306,429 rows and 8 columns. Irrelevant columns that did not contribute to the epidemiological analysis—specifically `SNo` (Serial Number) and `Last Update` (which contained redundant timestamp formats)—were dropped to reduce memory usage and streamline the dataset.
* **Data Type Standardization:** * The `ObservationDate` column was originally an 'object' (string). It was explicitly cast to a standard `datetime64[ns]` format. This is a critical step for time-series analysis, allowing for chronological sorting and filtering.
    * The core epidemiological metrics—`Confirmed`, `Deaths`, and `Recovered`—were cast to integers (`int64`) to prevent floating-point errors during aggregation.
* **Feature Engineering (Active Cases):** A new, vital metric called **Active Cases** was derived. While "Confirmed" shows the historical total, "Active" cases indicate the current burden on a region's healthcare system at any given time. This was calculated using the formula:
    `Active = Confirmed - Recovered - Deaths`
* **Handling Missing Values:** During the subsetting of Indian data, missing values (NaN) in the `Province/State` column were identified. To maintain data integrity without deleting valuable rows, these null values were filled using the statistical mode (the most frequent state) or categorized as 'Unknown'.

---

## 3. Global COVID-19 Data Analysis (Experiment 19)

To evaluate the current state of the pandemic globally, the dataset was filtered to extract the latest available observation date using the `max()` function, which returned May 29, 2021.

### Global Footprint
The filtering process yielded a snapshot of 765 data points across 195 unique countries and regions. By grouping this data by `Country/Region` and aggregating the numerical columns, we obtained the total cumulative figures for every nation.

### Geospatial Visualization
Using Plotly Express, a global choropleth map was generated (`locations="Country/Region"`). This color-coded map provided immediate visual context, highlighting hotspots in North America, South America, and South Asia based on confirmed case intensity.



### Top 5 Most Affected Countries
Sorting the aggregated data revealed the nations with the highest cumulative caseloads as of late May 2021:

| Rank | Country/Region | Total Confirmed Cases | Total Recovered Cases | Total Deaths |
| :---: | :--- | :--- | :--- | :--- |
| **1** | United States | 33,251,939 | 0 * | 594,306 |
| **2** | India | 27,894,800 | 25,454,320 | 325,972 |
| **3** | Brazil | 16,471,600 | 14,496,224 | 461,057 |
| **4** | France | 5,719,877 | 390,878 | 109,518 |
| **5** | Turkey | 5,235,978 | 5,094,279 | 47,271 |

> *(Note: The '0' recovered cases for the US represents a reporting anomaly in the source dataset for that specific date, highlighting the importance of data validation in real-world scenarios.)*

---

## 4. India-Specific COVID-19 Analysis (Experiment 20)

The second phase of the project shifted focus entirely to India. By filtering the dataset (`data['Country/Region'] == "India"`), a new DataFrame comprising 13,182 rows was created. This localized analysis is particularly poignant, as May 2021 coincided with the peak of India's devastating "second wave" of infections.

### Regional Breakdown
The data revealed that cases were tracked across 38 distinct entities, encompassing all states and union territories. Grouping the data by `Province/State` for the latest observation date allowed us to see exactly where the virus was most concentrated.

### Advanced Mapping with GeoJSON
To visualize this regional data, standard country names were insufficient. A custom GeoJSON file (`india.json`) containing the exact geographical coordinates of Indian state borders was integrated. By matching the feature key (e.g., `properties.st_nm`) in the GeoJSON to the `Province/State` column in our DataFrame, a highly detailed, interactive map of India was generated using a purple color scale to depict case density.



### Top 5 Most Affected States in India
The state-wise aggregation highlighted severe regional disparities in how the pandemic spread, largely correlating with highly urbanized and densely populated states.

| Rank | Province/State | Confirmed Cases | Deaths | Recovered Cases |
| :---: | :--- | :--- | :--- | :--- |
| **1** | Maharashtra | 5,713,215 | 94,030 | 5,339,838 |
| **2** | Karnataka | 2,567,449 | 28,298 | 2,189,064 |
| **3** | Kerala | 2,494,385 | 8,455 | 2,252,505 |
| **4** | Tamil Nadu | 2,039,716 | 23,261 | 1,706,298 |
| **5** | Uttar Pradesh | 1,688,152 | 20,208 | 1,621,743 |

---

## 5. Key Insights and Inferences

* **Concentration of Cases:** In India, the western and southern peninsular states (Maharashtra, Karnataka, Kerala, Tamil Nadu) bore the heaviest initial and secondary brunt of the pandemic. Maharashtra alone accounted for roughly 20% of the entire country's confirmed cases by this date.
* **Mortality vs. Caseload:** While Kerala had the third-highest number of confirmed cases, its death toll (8,455) was significantly lower than states with fewer cases like Delhi (24,073 deaths, ranked 6th in cases). This suggests variations in healthcare infrastructure, reporting mechanisms, or regional virus variants.
* **The Power of Visualization:** The use of choropleth maps proved essential. Tabular data alone makes it difficult to quickly grasp spatial relationships. The maps instantly communicated which borders were experiencing outbreaks, which is critical for real-world logistical planning (e.g., oxygen and vaccine distribution).

---

## 6. Conclusion

This project successfully demonstrates the end-to-end process of data analysis using Python. By cleaning, engineering, and visualizing the `covid_19_data.csv` dataset, we were able to quantify the massive scale of the pandemic up to May 2021. The global analysis confirmed the US, India, and Brazil as the epicenters of the outbreak. Furthermore, the localized mapping of India using GeoJSON boundaries provided a clear, data-driven picture of the regional crises unfolding across states like Maharashtra and Karnataka. Ultimately, this experiment underscores the vital role of data science in tracking, understanding, and communicating the realities of global public health emergencies.
