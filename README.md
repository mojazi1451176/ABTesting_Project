# ABTesting_Project
Analyzing a newsroom's dataset to find out if conversions increase/decrease for a newly created page. 

# A/B Testing Analysis Using Python

## Overview
This project analyzes an A/B test dataset to determine whether a new landing page results in higher engagement and conversions than an existing one. The script performs data exploration, visualization, and statistical tests to draw meaningful insights.

## Requirements
Ensure you have the following Python packages installed before running the script:

- `scipy`
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `statsmodels`

You can install the required packages using:
```bash
pip install scipy pandas numpy matplotlib seaborn statsmodels
```

## Dataset
The script reads the dataset `abtest.csv`, which contains the following columns:
- `user_id`: Unique identifier for each user
- `group`: Control or treatment group assignment
- `landing_page`: Whether the user was shown the old or new landing page
- `time_spent_on_the_page`: Time spent on the page in seconds
- `converted`: Whether the user converted (`yes` or `no`)
- `language_preferred`: User's preferred language

## Steps Performed

### 1. Data Loading and Exploration
- Reads the dataset into a pandas DataFrame
- Checks the first and last five rows
- Displays dataset shape and column data types
- Generates summary statistics for numerical and categorical variables
- Identifies missing values and duplicate rows

### 2. Data Visualization
- Boxplots and histograms for `time_spent_on_the_page`
- Count plots for categorical variables (`group`, `landing_page`, `converted`, `language_preferred`)
- Boxplots to compare:
  - `landing_page` vs. `time_spent_on_the_page`
  - `converted` vs. `time_spent_on_the_page`
  - `language_preferred` vs. `time_spent_on_the_page`

### 3. Statistical Analysis

#### **Hypothesis 1: Do users spend more time on the new landing page?**
- Uses an independent t-test to compare `time_spent_on_the_page` for old vs. new landing pages.
- Null Hypothesis: Users spend equal time on both pages.
- Alternative Hypothesis: Users spend more time on the new landing page.
- The script calculates the p-value and determines statistical significance.

#### **Hypothesis 2: Is the conversion rate higher for the new landing page?**
- Uses a chi-square test to check differences in conversion rates.
- Uses a proportion z-test to compare conversion rates between the control and treatment groups.
- Null Hypothesis: Conversion rates are equal.
- Alternative Hypothesis: Conversion rate is higher for the new page.

## Results & Interpretation
- The t-test and p-value indicate that users spend significantly more time on the new landing page.
- The chi-square and proportion z-test suggest that the new landing page has a significantly higher conversion rate.
- Thus, there is strong evidence to support the new landing page.

## Usage
1. Place `abtest.csv` in the specified directory.
2. Run the script using:
   ```bash
   python ab_testing.py
   ```
3. Analyze the outputs and visualizations to make data-driven decisions.

## Author
Mo Jazi

