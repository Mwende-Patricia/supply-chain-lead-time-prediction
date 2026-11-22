# Supply Chain Lead Time Prediction

A machine learning model that predicts supply chain shipping times from order data. Built with Python, Pandas, and Scikit-learn.

![Python](https://img.shields.io/badge/Python-3.13-blue)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Random%20Forest-orange)

## Overview
Late deliveries disrupt supply chains and frustrate customers. This project uses a **Random Forest regression** model to predict shipping lead times, so delays can be anticipated earlier and planned for.

It was developed as my final-year Operations Research project at JKUAT.

## Dataset
- 399 orders, 43 columns
- Includes shipping mode, delivery status, order value, discounts, customer location, and product details
- Targets: **scheduled shipping days** and **real shipping days**

## Approach
1. **Data cleaning:** checked for missing values and duplicates, and dropped two columns that were almost entirely empty (Order Zipcode, Product Description).
2. **Exploratory analysis:** compared real and scheduled shipping days and looked at the spread of delivery statuses.
3. **Encoding:** converted text columns into numeric dummy variables.
4. **Feature selection:** used Random Forest feature importance to narrow the variables down to the 10 most important.
5. **Modelling:** split the data 70% training and 30% testing, then trained a Random Forest regressor.
6. **Tuning:** tested 81 hyperparameter combinations with GridSearchCV (3-fold cross-validation).

## Results
Tested on 120 orders the model had not seen:

| Metric | Value | What it means |
|---|---|---|
| Mean absolute error | 0.28 days | Predictions are off by about a quarter of a day on average |
| Median absolute error | 0.19 days | A typical prediction is off by under 5 hours |
| RMSE | 0.57 days | Penalises larger misses more heavily |
| R² | 0.81 | The model explains about 81% of the variation in shipping times |

Hyperparameter tuning gave a very small improvement, which suggests the model was already close to its best on this data.

## Tools Used
- Python
- Pandas and NumPy
- Scikit-learn
- Matplotlib and Seaborn
- Jupyter Notebook

## How to Run
1. Clone or download this repository.
2. Install the libraries: `pip install pandas numpy scikit-learn matplotlib seaborn openpyxl missingno`
3. Open `Lead Time Prediction Model.ipynb` in Jupyter Notebook.
4. Update the data file path in the first cells to where your dataset is saved.
5. Run all cells.

## Next Steps
- Test the model on a larger dataset
- Review which input features are available at prediction time and refine the feature set
- Compare against other models such as Gradient Boosting

## Files
- `Lead Time Prediction Model.ipynb`: full analysis, model training, and evaluation

## Author
**Patricia Mwende Mutuku**
BSc Operations Research, JKUAT
[LinkedIn](https://linkedin.com/in/patricia-mwende)
