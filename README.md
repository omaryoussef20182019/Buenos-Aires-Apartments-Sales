# Buenos Aires Apartment Price Prediction

## Project Overview

This data science project is aimed at building a robust machine learning model to **predict the sale price of apartments in Buenos Aires, Argentina**. It employs a supervised learning pipeline, utilizing features such as covered surface area, geographic coordinates, and neighborhood to estimate the price.

## Repository Contents

* **`buino aries (1) (1).ipynb`**: The main Jupyter Notebook that covers the entire modeling process, including data cleaning, exploratory analysis, pipeline construction, model training (Ridge Regression), evaluation, and the final prediction function.
* **`buenos-aires-housing-data.csv`** (Assumed): The raw dataset used for training and testing the model.

## Methodology

### Data Wrangling and Preparation
1.  **Custom `wrangle` Function:** A specialized function was created to load and clean the raw data, ensuring only relevant apartment listings are kept and feature names are standardized.
2.  **Feature Selection:** The model uses key features: `'surface_covered_in_m2'`, `'lat'`, `'lon'`, and `'neighborhood'` to predict the target variable `'price'`.

### Modeling Pipeline
A Scikit-learn pipeline was implemented to automate and standardize the preprocessing and modeling steps:
1.  **OneHotEncoder:** Applied to the categorical feature `'neighborhood'` to convert it into a format suitable for the linear model.
2.  **Ridge Regression:** Chosen as the core regression algorithm, which is effective for handling potential multicollinearity in real estate data.

### Evaluation and Deployment
* The model's performance was measured using the **Mean Absolute Error (MAE)** to quantify the average prediction error.
* A convenient function, `make_prediction(area, lat, lon, neighborhood)`, was developed for easy price forecasting based on user-specified apartment characteristics.

## Key Technologies and Libraries

* **Python**
* **pandas & numpy**: For data handling and numerical operations.
* **scikit-learn (sklearn)**: For `Ridge` Regression, `make_pipeline`, `OneHotEncoder`, and `mean_absolute_error`.
* **seaborn & plotly.express**: For data visualization (EDA and results visualization).
* **ipywidgets**: For creating interactive prediction tools (if used in the notebook).

## Example Prediction

The notebook concludes with a functional example of the `make_prediction` function:

```python
# Example prediction for an apartment in Villa Crespo
make_prediction(110, -34.60, -58.46, "Villa Crespo")
# Predicted apartment price: $255190.04 (Example output)
