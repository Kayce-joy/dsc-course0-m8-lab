## Aviation Accident Data Analysis
### Project Overview
This project examines past flight accident logs to find the aircraft manufacturers and models with the best safety records. The goal is to deliver data-backed purchase recommendations for a company looking to buy both small and large aircraft.

The project consists of two major stages:

- Data Cleaning
- Exploratory Data Analysis (EDA)
The analysis was performed using Python with Pandas, Matplotlib, and Seaborn.

### Business Problem
The client wants to know which aircraft makes/models with the strongest safety records, by examining:

* Fatal and serious injury rates
* Aircraft destruction rates
* The impact of operational factors such as weather conditions and Number of engines.
* Separate recommendations were developed for small aircraft (less than 20 passengers) and large aircraft (20 or more passengers).

### Dataset
The dataset contains historical aviation accident records from the National Transportation Safety Board (NTSB).
Source: https://www.kaggle.com/datasets/mos3santos/acidentes-de-aviao-at-2023



### Preprocessing and Cleaning 
* **Filtering Logic:** Isolated standard airplane operations by filtering `Aircraft.Category` and extracted valid accident data points.
* **Text Standardization:** Normalized string casing and formatting for the columns to resolve duplications.
* **Column Selection:** Dropped sparse or operationally irrelevant metrics (such as geographical variables or specific code columns) 
* **Feature Construction:** Engineered the boolean `Aircraft_Destroyed` variable from `Aircraft.damage`, built the combined `Plane_Type` label, and calculated `Fatal_Serious_Count`.

---

## Analytical Insights


### 1. Strategic Manufacturer Evaluation (`Make`)
* **General Aviation Class:** `Cessna` (7,029 accidents) and `Piper` (3,938 accidents) dictate the data baseline for small planes due to high volume. Conversely, `Cirrus` models exhibit an elevated risk footprint, with average injury rates exceeding 43% and a 27.6% destruction rate.
* **Commercial Fleet Class:** `Boeing` provides the most dense and dependable dataset for large planes (553 records), maintaining low average passenger injury fractions (~11.8%) and sub-10% hull destruction rates. 
* **Distribution Profiles:** Violin distributions for small-scale manufacturers show a very wide, bulged base centered exactly at 0.0 (no serious injuries), with needle-thin lines running to 1.0. Commercial scatter plots reveal heavy data concentrations directly on the 0.0 line, proving high baseline passenger survivability.

### 2. Individual Airframe Analysis (`Plane_Type`)
* **Small Airframes:** The `Cessna 172SP` (12 accidents) and `Maule M-5-210C` (11 accidents) delivered a flawless **0.00% average injury rate** in this dataset window.
* **Large Airframes:** Mainline commercial jets lead the industry, with the `Boeing 777` (19 accidents) and `Boeing 757` (16 accidents) showing near-zero average occupant injury fractions (~0.14% and ~0.16%).

### 3. Engine Count Imbalance (`Number.of.Engines`)
* **Volume Disconnect:** Records with `Number.of.Engines` at `1.0` (13,138 cases) and `2.0` (1,940 cases) make up 99.7% of the dataset, forming our only statistically sound samples.
* **The Twin-Engine Paradox:** Aircraft with `2.0` engines display higher average injury rates (~32%) and higher `Aircraft_Destroyed` averages (~17%) within accident logs than single-engine configurations (~25% injury, ~7% destruction). Because twin powerplants provide operational redundancy to avoid simple landing incidents, an entry in this dataset usually indicates a far more complex or high-speed operational crisis.
* **Statistical Gaps:** Counts for `0.0`, `3.0`, and `4.0` engines combine for only 47 total records. Their extreme spikes or drops are artifacts of low data volume rather than accurate indicators of risk.

---

##  Recommendations

### Small Aircraft Options
* **Primary Recommendation:** Fleet selection should favor `Maule` models (such as the `Maule M-5-210C`) due to low historical injury metrics (~16%).
* **High-Volume Deployment:** The `Cessna 172SP` serves as the optimal standard for flight instruction or high-utilization utility tasks due to its proven zero-injury baseline.
* **Hull Protection:** For assets prioritizing physical durability, `Luscombe` and `Grumman-Schweizer` keep hull destruction rates below 2%.

### Large Aircraft Options
* **Primary Recommendation:** Mainline `Boeing` aircraft—specifically the `Boeing 777` and `Boeing 757` variants—are heavily recommended due to their unmatched track record of keeping occupant injury rates close to zero during recorded incidents.
* **Structural Alternative:** `Dehavilland` configurations are outstanding options for airframe longevity, maintaining a remarkably low 2.4% destruction rate.

---

## Technologies Used
* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn

