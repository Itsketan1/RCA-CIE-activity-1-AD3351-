# Activity 2: Simple House Price Prediction

**Course:** Machine Learning  
**Unit:** Unit II – Supervised Learning: Regression  
**Department:** Artificial Intelligence & Data Science  
**Institution:** Zeal College of Engineering and Research, Pune  
**Academic Year:** 2026–27

## Project Overview

This project builds a **Simple Linear Regression** model to predict house prices using the USA Housing dataset. It uses **Average Area Income** as the single input feature and **Price** as the continuous numerical target.

The notebook is organized with Markdown headings and short explanations for each stage of the activity: dataset selection, inspection, cleaning, feature and target selection, visualization, train-test split, model training, prediction, evaluation, and conclusion.

## Dataset

- **Dataset:** USA Housing
- **Source:** [USA Housing CSV](https://raw.githubusercontent.com/VALENCEML/eBOOK/main/EN/08/USA_Housing.csv)
- **Description:** 5,000 property records and 7 columns: average area income, average area house age, average number of rooms, average number of bedrooms, area population, price, and address.
- **Input feature (X):** `Avg. Area Income`
- **Target (y):** `Price`

The **`USA_Housing.csv` file is included in this repository**. When the notebook is run from the repository folder, it loads this local CSV first. If the notebook is opened separately without the CSV (for example, by uploading only the notebook to Google Colab), it automatically falls back to the dataset source URL.

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Jupyter Notebook / Google Colab

## Repository Structure

```text
SIMPLE_HOUSE_PRICE_PREDICTION/
├── USA_Housing.csv
├── README.md
├── requirements.txt
└── ML_activity_2.ipynb
```

## Methodology

1. Load the USA Housing dataset, preferring the CSV included in the repository.
2. Inspect the first records, dimensions, data types, summary statistics, missing values, and duplicate records.
3. Remove duplicate records and rows with missing or invalid values in the selected feature and target.
4. Select average area income as the input feature and house price as the target.
5. Plot average area income against actual house prices.
6. Split the observations into 80% training and 20% testing sets (`random_state=42`).
7. Train a Scikit-learn `LinearRegression` model.
8. Predict prices for the held-out test observations.
9. Evaluate with MAE, MSE, RMSE, and R².
10. Plot actual versus predicted prices and make one new example prediction.

## Recorded Model Results

The values below are preserved from the executed notebook:

| Parameter | Result |
|---|---:|
| Dataset rows / columns | 5,000 / 7 |
| Training observations | 4,000 |
| Testing observations | 1,000 |
| Coefficient (slope) | 21.208906 |
| Intercept | -225,053.702872 |
| MAE | $216,826.35 |
| MSE | 74,194,887,058.66 |
| RMSE | $272,387.38 |
| R² | 0.396949 |

The fitted equation is approximately:

```text
Predicted Price = 21.208906 × Avg. Area Income − 225053.702872
```

The test R² of approximately **0.397** means the single-feature model explains about **39.7%** of the variation in test-set prices. The MAE of approximately **$216,826** indicates substantial average absolute prediction error.

## New Example Prediction

The notebook uses the median average-area income from the training set as a new input:

- **Average area income:** $68,926.42
- **Predicted house price:** $1,236,800.31

## How to Run

1. Clone or download this repository.
2. Open `ML_activity_2.ipynb` in Jupyter Notebook or upload it to [Google Colab](https://colab.research.google.com/).
3. Install the dependencies listed in `requirements.txt` if needed.
4. Run the cells in order. When run from the repository folder, the notebook uses the included CSV. When opened without the CSV, it uses the source URL as a fallback.

## Conclusion and Limitations

A Simple Linear Regression model was trained to estimate house prices from average area income and evaluated on a held-out test set. The results show that this single feature provides limited predictive power. House prices may also depend on location, property size, house age, number of rooms, facilities, and other factors. A useful next step would be to compare this baseline with a multiple linear regression model using additional relevant features.

---

*Machine Learning – Activity 2: Simple House Price Prediction*
