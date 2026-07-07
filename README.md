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

### 1. Airplane Manufacturer Review (`Make`)
* **Small Planes:** Cessna and Piper have the most accident records because they are the most common small planes. Cirrus planes show a much higher risk, with injuries occurring in over 43% of their accidents and a high rate of destroyed planes.
* **Large Planes:** Boeing provides the most reliable data for big planes. They keep passenger injury rates low and rarely suffer total plane destruction.
* **Safety Trends:** Charts for small manufacturers show that the vast majority of accidents result in zero serious injuries. Commercial flight charts reveal heavy data concentrations that prove high baseline passenger survivability.

### 2. Specific Airplane Models  (`Plane_Type`)
* **Small Models:** The Cessna 172SP and Maule M-5-210C both achieved a perfect 0% average injury rate during the recorded time frame.
* **Large Models:** The Boeing 777 and Boeing 757 lead the industry in safety, with average passenger injury rates close to zero

### 3. Engine Count Imbalance (Number.of.Engines)
* **Volume Disconnect:** Records for 1.0 and 2.0 engines make up 99.7% of the dataset, forming our only statistically sound samples.
* **The Twin-Engine Paradox:** Aircraft with 2.0 engines display higher average injury and destruction rates in these logs than single-engine configurations. Because twin engines provide a backup to avoid simple landing incidents, an entry in this dataset usually indicates a far more severe or high-speed operational crisis.
* **Statistical Gaps:** Counts for 0.0, 3.0, and 4.0 engines combine for very few total records. Their extreme spikes or drops are artifacts of low data volume rather than accurate indicators of risk.

---

##  Recommendations

### Small Aircraft Options
* **Best All-Around:** Choose Maule models (like the M-5-210C) for their strong safety record and low injury rates in past incidents.
* **Best for Training:** The Cessna 172SP is the top pick for flight instruction or high-utilization utility tasks. It is well-known for its excellent safety and injury-free record.
* **Most Durable:** For planes that hold up best during accidents, Luscombe and Grumman-Schweizer models rarely get badly damaged.

### Large Aircraft Options
* **Top Passenger Safety:** Mainline Boeing planes, especially the 777 and 757, are highly recommended because they have an amazing track record of keeping passengers safe in emergencies.
* **Longest Lasting:** Dehavilland aircraft are excellent for airframe longevity and maintaining durability.

---

## Technologies Used
* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn

