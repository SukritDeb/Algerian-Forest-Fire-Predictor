
# Algerian Forest Fire Predictor

This project analyzes and predicts forest fire weather indices (FWI) in Algeria using machine learning regression models. The workflow includes data cleaning, exploratory data analysis (EDA), feature engineering, and model training with various regularization techniques.

## Dataset
- **Algerian_forest_fires_dataset_UPDATE.csv**: Raw dataset containing meteorological and fire occurrence data for two regions in Algeria.
- **Algerian_forest_fires_dataset_Cleaned.csv**: Cleaned and preprocessed version of the dataset, ready for analysis and modeling.

## Notebooks
- **clean-and-eda.ipynb**: Data cleaning and exploratory data analysis (EDA). Steps include:
	- Handling missing values and fixing data types
	- Adding region labels
	- Visualizing feature distributions and class balance
	- Correlation analysis and outlier detection
	- Monthly fire analysis for each region
- **model-training.ipynb**: Machine learning workflow. Steps include:
	- Feature selection and encoding
	- Train-test split
	- Multicollinearity check and feature reduction
	- Feature scaling (standardization)
	- Model training and evaluation:
		- Linear Regression
		- Lasso Regression (with and without cross-validation)
		- Ridge Regression (with and without cross-validation)
		- ElasticNet Regression (with and without cross-validation)
	- Model performance metrics: MAE, MSE, RMSE, R²
	- Visualization of predictions vs. actual values

## Requirements
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

Install dependencies with:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Usage
1. **Data Cleaning & EDA**: Run `clean-and-eda.ipynb` to clean the raw dataset and perform exploratory analysis. This will generate the cleaned CSV file.
2. **Model Training**: Run `model-training.ipynb` to train and evaluate regression models on the cleaned data.

## Project Structure
```
├── Algerian_forest_fires_dataset_Cleaned.csv
├── Algerian_forest_fires_dataset_UPDATE.csv
├── clean-and-eda.ipynb
├── model-training.ipynb
├── README.md
```

## References
- [UCI Machine Learning Repository: Algerian Forest Fires Dataset](https://archive.ics.uci.edu/ml/datasets/Algerian+Forest+Fires+Dataset+)

## License
This project is for educational and research purposes only.