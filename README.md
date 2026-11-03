# Activity 2: Simple House Price Prediction

**Course:** Machine Learning  
**Unit:** Unit II – Supervised Learning: Regression  
**Department:** Artificial Intelligence & Data Science  
**Institution:** Zeal College of Engineering and Research, Pune  
**Academic Year:** 2026–27

## Project Overview

This project builds a **Simple Linear Regression** model to predict house prices using the USA Housing dataset. The model uses **Average Area Income** as its single input feature and **Price** as the continuous numerical target.

The notebook follows the activity workflow: dataset inspection, data cleaning, feature/target selection, visualization, an 80:20 train-test split, model training, test-set prediction, regression metrics, actual-versus-predicted visualization, and a new example prediction.

## Dataset

- **Dataset:** USA Housing
- **Source:** [USA Housing CSV](https://raw.githubusercontent.com/VALENCEML/eBOOK/main/EN/08/USA_Housing.csv)
- **Description:** 5,000 property records and 7 columns: average area income, average area house age, average number of rooms, average number of bedrooms, area population, price, and address.
- **Input feature (X):** `Avg. Area Income`
- **Target (y):** `Price`

The notebook first looks for `USA_Housing.csv` in the project directory. If the file is not present, it loads the dataset from the source URL.

### Download a local copy of the dataset (Windows PowerShell)

Run this command from the project directory to add the CSV file to your local project before pushing it to GitHub:

```powershell
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/VALENCEML/eBOOK/main/EN/08/USA_Housing.csv" -OutFile "USA_Housing.csv"
```

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Jupyter Notebook / Google Colab

## Repository Structure

```text
SIMPLE_HOUSE_PRICE_PREDICTION/
├── USA_Housing.csv          # Download using the command above
├── README.md
├── requirements.txt
└── ML_activity_2.ipynb
```

## Methodology

1. Load and inspect the USA Housing dataset.
2. Review data types, summary statistics, missing values, and duplicate records.
3. Remove duplicates and invalid/missing values in the selected feature and target.
4. Select average area income as the input feature and price as the target.
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

The test R² of approximately **0.397** means the single-feature model explains about **39.7%** of the variation in test-set prices. The MAE of approximately **$216,826** indicates substantial average absolute prediction error. R² is a comparison with a mean-based baseline; a negative test R² is possible in general.

## New Example Prediction

The notebook uses the median average-area income from the training set as a new input:

- **Average area income:** $68,926.42
- **Predicted house price:** $1,236,800.31

## How to Run

1. Clone or download this repository.
2. (Optional but recommended) Download `USA_Housing.csv` using the PowerShell command above.
3. Open `ML_activity_2.ipynb` in Jupyter Notebook or upload it to [Google Colab](https://colab.research.google.com/).
4. Install the dependencies listed in `requirements.txt` if needed.
5. Run the cells in order.

## Conclusion and Limitations

A Simple Linear Regression model was trained to estimate house prices from average area income and evaluated on a held-out test set. The results show that this single feature provides limited predictive power. House prices may also depend on location, property size, house age, number of rooms, facilities, and other factors. A useful next step would be to compare this baseline with a multiple linear regression model using additional relevant features.

---

*Machine Learning – Activity 2: Simple House Price Prediction*
