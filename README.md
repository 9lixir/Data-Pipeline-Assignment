# Airline Delay Analysis & ETL Pipeline

This project implements a complete **ETL (Extract, Transform, Load)** pipeline and **Exploratory Data Analysis (EDA)** on US Flight Delay data. The goal is to identify the primary drivers of flight disruptions and prepare a clean dataset for machine learning.

## Project Overview
The pipeline processes raw airline performance data, handles extreme outliers using statistical scaling, and visualizes complex relationships between flight volumes and various delay causes (Carrier, Weather, NAS, and Security).

## Tech Stack
* **Language:** Python 3.x
* **Data Handling:** Pandas
* **Preprocessing:** Scikit-Learn (RobustScaler)
* **Visualization:** Matplotlib, Seaborn

## Project Structure
* `Data_Pipeline_Assignment.ipynb`: Main Jupyter Notebook containing the ETL and EDA code.
* `Cleaned_Airline_Delay_Cause.csv`: The final processed dataset ready for modeling.
* `requirements.txt`: Project dependencies for environment reproduction.
* `README.md`: Project documentation.

## Key Insights from EDA

### 1. Correlation Heatmap

* **Finding:** A near-perfect correlation (**0.97**) exists between the number of delayed flights and total delay minutes. 
* **Primary Driver:** **Late Aircraft Delay** is the strongest predictor of total delay time ($r = 0.92$), confirming a significant "domino effect" in airline scheduling.

### 2. Distribution & Outliers

* **Finding:** The data is heavily right-skewed with extreme outliers exceeding **400,000 minutes**.
* **Action:** **RobustScaler** was utilized to standardize the data, as it uses the median and Interquartile Range (IQR) which are not distorted by these extreme values.

### 3. Multi-Variable Analysis (Pairplot)

* **Finding:** Most delay causes show an "L-shaped" distribution, meaning that while extreme delays exist, the majority of flights experience minimal to no delay for specific categories.

## ⚙️ Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone <https://github.com/9lixir/Data-Pipeline-Assignment>
   cd Data-Pipeline-Assignment
   ```

2. **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

3. **Execute the Pipeline**
    Run the Jupyter notebook cells sequentially. The Script will:
    * Load the raw CSV.
    * Clean missing values and apply Robust Scaling.
    * Perform One-Hot Encoding on categorical features.
    * Export the Cleaned_Airline_Data.csv.
    * Generate  diagnostic visualizations.


