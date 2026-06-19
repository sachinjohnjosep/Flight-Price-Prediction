# Study Guide: Flight Price Prediction

Use this project to learn how a regression machine learning project is built from raw data to model evaluation.

## Order to Study

1. `notebooks/01_eda.ipynb`
   - Load the raw flight dataset.
   - Understand columns, missing values, data types, and basic statistics.
   - Create visualizations to see how ticket price changes by airline, class, stops, route, duration, and days left.

2. `notebooks/02_data_cleaning.ipynb`
   - Drop unnecessary columns.
   - Convert stops into numbers.
   - Create `log_duration`.
   - One-hot encode categorical variables.
   - Save the cleaned dataset as `data/flights_cleaned.csv`.

3. `notebooks/03_model_building.ipynb`
   - Split data into training and test sets.
   - Train multiple regression models.
   - Compare models using MAE, RMSE, R², and MAPE.
   - Tune Random Forest using GridSearchCV.
   - Study prediction errors using residual plots.

## What You Should Understand Before Posting on LinkedIn

- What problem you solved.
- Why this is a regression problem.
- What features affect ticket price.
- Why categorical variables need encoding.
- What MAE, RMSE, R², and MAPE mean.
- Why Random Forest performed better than Linear Regression.
- What you would improve next.

## GitHub Upload Steps

```bash
git init
git add .
git commit -m "Initial flight price prediction project"
git branch -M main
git remote add origin YOUR_GITHUB_REPO_LINK
git push -u origin main
```

## Suggested LinkedIn Post

Built a Flight Price Prediction project using Python and Scikit-learn.

What I did:

- Cleaned and analyzed Indian airline ticket data.
- Performed feature engineering and one-hot encoding.
- Compared multiple regression models.
- Evaluated performance using MAE, RMSE, R², and MAPE.
- Random Forest gave the best result with R² around 0.98.

Tech stack:
Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn.

This project helped me understand the full machine learning workflow from raw data to model evaluation.

GitHub link: YOUR_LINK

## Google Colab Check Before GitHub

Run this first in Colab:

```python
!unzip Flight-Price-Prediction-Study-Project.zip
%cd Flight-Price-Prediction-Study-Project
!pip install -r requirements.txt
```

Then open the notebooks from the `notebooks/` folder and run them in order.

The notebooks include a path setup cell. It helps the project run from Colab, local Jupyter, or the notebooks folder.

## Important Study Setting

In `03_model_building.ipynb`, the default setting is:

```python
SAMPLE_SIZE = 5_000
```

This keeps training fast while studying. After you understand the notebook, change it to:

```python
SAMPLE_SIZE = None
```

This trains on the full cleaned dataset.
