# -DS-4002-Project-2-M3-
This is the repository for analysis for Project 2 in DS 4002

## Section 1: Software and Platform

### Platform: Google Colab + Jupyter Notebook
### Language: Python 3
### Key Packages:
  - Pandas (data manipulation)
  - Numpy (numerical operation)
  - Xgboost (classification model)
  - SARIMAX (forecasting model)
  - Sklearn (evaluation metrics)

### This project was deveopled on MacOS and Windows

## Section 2: File Structure
```
├DS-4002-Project-2-M3/
│
├── DATA/ # Raw and processed data files
│ ├── ORIGINALDATA.md # This provides the source of the data, providing a link to download them
│ ├── amazon-purchases.csv # Obtained from ORIGINALDATA.md, a list of amazon purchases with metadata
│ ├── survey.csv # A list of survey responses that relate to the purchases made with a unique identifier
│ ├── PREPROCCESEDDATA.md # Explains how to get the preprocessed data
│ └── process-purchases.csv # Combines amazon-purchases.csv and survey.csv, omitting uneeded columns and rows
│
├── OUTPUT/ # Generated charts and figures for reporting
│ ├── category_counts.png # Output graph produced by surface level analysis notebook Category.ipynb that displays counts for top 20 categories
│ └── monthly_purchases.png # Output graph produced by surface level analysis notebook Month.ipynb that displays counts for every mont 
│
├── SCRIPTS/ # Jupyter notebooks for analysis
│ ├── Categories.ipynb # Notebook for surface level analysis of how many purchases made in the top 20 categories
│ ├── Month.ipynb # Notebook for surface level analysis of how many purchases made in each month
│ ├── Preprocessing.ipynb # Preproccesses the original data by joining the two csv files and getting rid of any rows with missing data
│ ├── FeatureImportance.ipynb # Uses forecasting with demographic data to figure out what demographics are the most imporant when it comes to forecasting purchases
│ └── Project_2_MI3 # Uses forecasting to create predict general recommedations on what someone may be likely to purchases next
│
├── README.md # Project overview and instructions
└── LICENSE # License file
```


## Section 3: How To Reproduce

### 1. Set Up the Project Structure
Clone this repository and ensure your local folder structure matches the layout shown in **Section 2** of this README:

### 2.  Run Preprocessing
Open and run the notebook [Prepocessing.ipynb](https://github.com/Bubcheeseburger/-DS-4002-Project-2-M3-/blob/main/SCRIPTS/Preprocessing.ipynb):
This notebook will:
- Load (`amazon-purchases.csv` and `survey.csv`).
- Join to the two tables using 'Survey ResponseID'.
- Remove any rows with missing data values
- Output a new, processed dataset:  
  **`../DATA/process-purchases.csv`**

### 3. Run Forecasting Models and Category Predictions
Open and run the notebook [FeatureImportance.ipynb](https://github.com/Bubcheeseburger/-DS-4002-Project-2-M3-/blob/main/SCRIPTS/FeatureImportance.ipynb) and [Project_2_MI3](https://github.com/Bubcheeseburger/-DS-4002-Project-2-M3-/blob/main/SCRIPTS/Project_2_MI3.ipynb)
- Both load (`process-purchases.csv`)
- Include exogeneous variables like pre-holiday for better accuracy
- Train a SARIMAX forecasting model
- Predict future sales and test for accuracy
- XGBoost classification model to predict category purchases
- FeatureImportance.ipynb performs based on demographics and Project_2_MI3 does a general prediction.


