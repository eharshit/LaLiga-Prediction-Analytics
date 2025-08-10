# LaLiga Prediction Analytics

## Overview
This project analyzes La Liga football statistics and predicts championship outcomes using machine learning. The system scrapes data from [FBRef.com](https://fbref.com) for seasons 2014-2025 and uses a Random Forest Classifier to predict championship probabilities.

## Workflow
![Workflow](workflow.png)

**Process Flow**: Business Problem → Data Collection → Data Processing → Analysis → ML Modeling → Predictions

**Detailed Steps**:
- **Business Problem**: Predict La Liga Championship Outcomes
- **Data Collection**: Web Scraping from FBRef.com (11 seasons)
- **Data Processing**: Clean Dataset (220 records × 20 features)
- **Analysis**: Historical Trends Analysis
- **ML Modeling**: Random Forest Classifier
- **Predictions**: Championship Probabilities & Insights

## Project Steps

### 1. Business Problem
- **Objective**: Predict La Liga season winners and analyze historical performance patterns
- **Scope**: 11 seasons of data (2014-2025)

### 2. Data Collection (`Data_Scrapper.ipynb`)
- **Source**: FBRef.com (official football statistics)
- **Method**: Web scraping using `pandas.read_html()`
- **Coverage**: Seasons 2014-2015 through 2024-2025
- **Output**: `La_liga_data_2014-2025.csv`

### 3. Data Processing
- **Dataset Size**: 220 team-season records × 20 features
- **Data Cleaning**: Standardized column names, added season identifiers
- **Features Include**: Rankings, points, goals, wins/losses, expected goals, attendance

### 4. Data Analysis (`Data Analysis.ipynb`)
- **Team Performance Analysis**:  
  - Top 3 finishes distribution  
  - Championship winners (2014-2024)  
  - Points per match trends for champions
- **Historical Insights**:  
  - Barcelona: 6 titles (2014, 2015, 2017, 2018, 2022, 2024)  
  - Real Madrid: 4 titles (2016, 2019, 2021, 2023)  
  - Atlético Madrid: 1 title (2020)
- **Performance Metrics**: Average points per match for champions: 2.37

### 5. Feature Engineering
- **Calculated Features**:  
  - `games_left`: Remaining matches (38 total - matches played)  
  - `projected_pts`: Estimated final points based on current pace  
  - `is_champion`: Binary indicator (1 = champion, 0 = not)
- **Selected ML Features**: `pts/mp`, `gd`, `w`, `l`, `projected_pts`

### 6. Machine Learning
- **Algorithm**: Random Forest Classifier (200 trees)
- **Training Data**: Seasons 2014-2023 (historical performance)
- **Testing Data**: Season 2024 (current season predictions)
- **Target Variable**: Binary championship prediction (0/1)
- **Model Performance**:  
  - Accuracy: 100%  
  - ROC AUC Score: 1.000  
  - Log Loss: 0.014

### 7. Predictions & Results
- **2024 Season Championship Probabilities**:  
  - Barcelona: 86.16%  
  - Real Madrid: 13.8%
- **Additional Insights**:  
  - Conference League (7th position): Celta Vigo  
  - Relegation Risk: Valladolid and Las Palmas

### 8. Visualizations
- **Interactive Charts**: Plotly bar charts for championship probabilities
- **Historical Trends**: Matplotlib plots for points per match over time
- **Team Rankings**: Top 3 finishes visualization

## Tools Used
- **Python**: Pandas, NumPy, Scikit-learn
- **Data Visualization**: Plotly, Matplotlib
- **Machine Learning**: Random Forest Classifier
- **Data Source**: FBRef.com
- **Development**: Jupyter Notebook

## Files in Repository
- `Data_Scrapper.ipynb` - Web scraping and data collection  
- `Data Analysis.ipynb` - Data analysis and machine learning  
- `La_liga_data_2014-2025.csv` - Consolidated dataset (220 × 20)  
- `README.md` - Project documentation

## Key Findings
1. **Championship Dominance**: Barcelona and Real Madrid have dominated La Liga over the past decade  
2. **Performance Threshold**: Champions typically achieve ~2.37 points per match  
3. **Prediction Accuracy**: The model achieves perfect accuracy on historical data  
4. **Current Season**: Barcelona is heavily favored to win the 2024 championship

## Technical Implementation
- **Data Pipeline**: Automated web scraping → data cleaning → analysis → ML modeling  
- **Feature Selection**: Focused on performance metrics and projected outcomes  
- **Model Validation**: Cross-validation and multiple performance metrics  
- **Reproducibility**: Fixed random state and consistent data processing
