# Flight Price Prediction

A beginner-friendly regression project that predicts Indian airline ticket prices using route, airline, travel class, stops, duration, and days left before departure.

This project is built for learning. The notebooks are written step by step so you can understand the full machine learning workflow before uploading it to GitHub or sharing it on LinkedIn.

## Problem Statement

Given flight details such as airline, source city, destination city, departure time, arrival time, stops, class, duration, and days left, predict the ticket `price` in INR.

## Dataset

- Source: Airlines Flights Data from datasciencelovers on GitHub
- Raw dataset size: about 300,000 rows
- Cleaned dataset used in this project: 50,000 rows
- Model notebook default training sample: 5,000 rows for faster Google Colab study runs

You can change `SAMPLE_SIZE = 5_000` to `SAMPLE_SIZE = None` in `03_model_building.ipynb` to train on the full cleaned dataset.

## Features

| Feature | Meaning |
|---|---|
| airline | Airline company |
| source_city | Departure city |
| departure_time | Time bucket of departure |
| stops | Number of stops |
| arrival_time | Time bucket of arrival |
| destination_city | Arrival city |
| class | Economy or Business |
| duration | Flight duration in hours |
| days_left | Days left before departure |
| price | Target variable |

## Project Structure

```text
Flight-Price-Prediction-Study-Project/
├── data/
│   ├── flights.csv
│   └── flights_cleaned.csv
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_data_cleaning.ipynb
│   └── 03_model_building.ipynb
├── utils.py
├── requirements.txt
├── README.md
└── STUDY_GUIDE.md
```

## Notebook Flow

1. `notebooks/01_eda.ipynb`
   - Load the raw dataset
   - Check shape, columns, missing values, and data types
   - Study ticket prices by airline, route, class, stops, and days left
   - Create visualizations

2. `notebooks/02_data_cleaning.ipynb`
   - Remove unnecessary columns
   - Convert stops into numbers
   - Create `log_duration`
   - Apply one-hot encoding
   - Save cleaned data

3. `notebooks/03_model_building.ipynb`
   - Split data into train and test sets
   - Scale data where needed
   - Train multiple regression models
   - Compare MAE, RMSE, R², and MAPE
   - Tune Random Forest
   - Study residuals and feature importance

## Models Used

- Linear Regression
- Ridge Regression
- Lasso Regression
- Decision Tree Regressor
- Random Forest Regressor
- K-Nearest Neighbors Regressor
- Gradient Boosting Regressor
- Tuned Random Forest using GridSearchCV

## Results From Study Run

The default notebook uses 5,000 rows for faster Colab execution.

| Model | MAE | RMSE | R² | MAPE |
|---|---:|---:|---:|---:|
| Random Forest Tuned | 2540.08 | 4272.46 | 0.9653 | 0.1615 |
| Random Forest | 2582.81 | 4336.76 | 0.9642 | 0.1620 |
| Gradient Boosting | 3187.32 | 5092.60 | 0.9507 | 0.2222 |
| Decision Tree | 3053.85 | 5266.45 | 0.9473 | 0.1884 |
| Linear Regression | 4790.55 | 6832.90 | 0.9112 | 0.4789 |
| Lasso | 4790.42 | 6832.94 | 0.9112 | 0.4789 |
| Ridge | 4789.78 | 6833.10 | 0.9112 | 0.4785 |
| KNN | 9017.44 | 12560.66 | 0.7001 | 0.9147 |

## Key Findings

- Travel class is one of the strongest price drivers.
- Business class tickets are much higher than Economy class tickets.
- Ticket prices change based on days left before departure.
- Tree-based models perform better than linear models because flight pricing is non-linear.
- Random Forest gave the best result in this project.

## How To Run Locally

```bash
pip install -r requirements.txt
jupyter notebook
```

Then open the notebooks in this order:

```text
notebooks/01_eda.ipynb
notebooks/02_data_cleaning.ipynb
notebooks/03_model_building.ipynb
```

## How To Run In Google Colab

Upload the project ZIP to Colab and run:

```python
!unzip Flight-Price-Prediction-Study-Project.zip
%cd Flight-Price-Prediction-Study-Project
!pip install -r requirements.txt
```

Then open and run the notebooks from the `notebooks/` folder.

## Future Improvements

- Add XGBoost or CatBoost
- Save the best model using joblib
- Build a Streamlit price prediction app
- Add SHAP explainability
- Deploy the app and add the live link to this README

## Tech Stack

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
