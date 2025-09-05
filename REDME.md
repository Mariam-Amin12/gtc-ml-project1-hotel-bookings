# Hotel Booking Data Analysis Project

## 📊 Project Overview

This project performs comprehensive exploratory data analysis (EDA) and preprocessing on hotel booking data to understand booking patterns, cancellation trends, and customer behavior. The analysis includes data cleaning, feature engineering, outlier detection, and preparation for machine learning models.

## 🎯 Objectives

- Analyze hotel booking patterns and customer behavior
- Identify factors that influence booking cancellations
- Clean and preprocess data for machine learning applications
- Create meaningful features for predictive modeling
- Visualize key insights through data exploration

## 📁 Project Structure

```
GTC/
├── index.ipynb          # Main analysis notebook
├── REDME.md            # Project documentation
├── titanic.csv         # Additional dataset
└── hotel_bookings.csv  # Main dataset (not included in repo)
```

## 📋 Dataset Information

The project uses a hotel booking dataset containing information about:
- Hotel types and booking details
- Customer demographics and preferences  
- Booking dates and duration
- Cancellation status
- Special requests and requirements

**Note**: You'll need to obtain the `hotel_bookings.csv` dataset and place it in the project directory.

## 🛠️ Technologies Used

- **Python 3.x**
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations
- **Matplotlib** - Data visualization
- **Seaborn** - Statistical data visualization

## 🔍 Analysis Workflow

### 1. Data Loading and Initial Exploration
- Load hotel booking dataset
- Examine data structure and basic statistics
- Identify data types and missing values

### 2. Data Cleaning
- **Missing Value Treatment**:
  - Children column: Fill with 0 (indicates no children)
  - Country column: Fill with 'Unknown' for missing entries
  - Drop company and agent columns (non-critical features)
- **Duplicate Removal**: Identify and remove duplicate records
- **Data Type Conversion**: Convert date columns to proper datetime format

### 3. Feature Selection
- Remove irrelevant features:
  - `arrival_date_week_number`
  - `babies`
  - `reservation_status_date`
  - `required_car_parking_spaces`

### 4. Outlier Detection and Treatment
Applied outlier removal with specific thresholds:
- Days in waiting list: ≤ 250
- Average daily rate (ADR): ≤ 150
- Total special requests: ≤ 2
- Children: ≤ 8
- Adults: ≤ 10
- Weekend nights: ≤ 5
- Week nights: ≤ 6
- Lead time: ≤ 230

### 5. Feature Engineering
Created new meaningful features:
- **Total guests**: Sum of adults and children
- **Total nights**: Sum of weekend and week nights
- **Is family**: Binary indicator for bookings with children

### 6. Data Encoding
- **One-Hot Encoding**: Applied to low-cardinality categorical variables
- **Frequency Encoding**: Used for high-cardinality features
- **Category Grouping**: Grouped infrequent categories as 'Other'

### 7. Correlation Analysis
- Analyzed feature correlations with target variable (`is_canceled`)
- Generated correlation matrix heatmap for numerical features

## 📈 Key Features Analyzed

- Hotel type and booking channels
- Market segments and customer types
- Room types and meal preferences
- Booking lead times and special requests
- Geographic distribution (country analysis)
- Seasonal booking patterns

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Running the Analysis
1. Clone this repository
2. Ensure `hotel_bookings.csv` is in the project directory
3. Open `index.ipynb` in Jupyter Notebook or VS Code
4. Run all cells sequentially

## 📊 Expected Outputs

- Data quality reports and missing value visualizations
- Outlier detection boxplots
- Feature correlation analysis
- Cleaned and preprocessed dataset ready for modeling
- Feature importance insights



