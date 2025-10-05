

# Algerian Forest Fire Predictor

This project provides a complete pipeline for analyzing, modeling, and predicting the Forest Fire Weather Index (FWI) in Algeria using machine learning. It includes data cleaning, exploratory data analysis (EDA), model training, and a web application for real-time prediction.

## Features
- **Data Cleaning & EDA**: Jupyter notebooks for cleaning and exploring the Algerian forest fire dataset.
- **Model Training**: Multiple regression models (Linear, Lasso, Ridge, ElasticNet) with cross-validation and feature engineering.
- **Web Application**: Flask-based web app for predicting FWI from user input.

## Dataset
- `notebooks/Algerian_forest_fires_dataset_UPDATE.csv`: Raw dataset with meteorological and fire occurrence data for two Algerian regions.
- `notebooks/Algerian_forest_fires_dataset_Cleaned.csv`: Cleaned and preprocessed dataset.

## Notebooks
- `notebooks/clean-and-eda.ipynb`: Data cleaning, type fixing, region labeling, visualization, and correlation analysis.
- `notebooks/model-training.ipynb`: Feature selection, scaling, model training (including saving scaler and model as `.pkl`), and evaluation.

## Web Application
- `application.py`: Flask app that loads the trained Ridge regression model and scaler, provides a web interface for FWI prediction.
- `templates/index.html`: Welcome page.
- `templates/home.html`: Input form for prediction and result display.
- `models/ridge_model.pkl`, `models/scaler.pkl`: Saved model and scaler from training notebook.

## Requirements
- Python 3.x
- Flask
- numpy
- pandas
- scikit-learn

Install dependencies with:
```bash
pip install -r requirements.txt
```


## Usage
1. **Data Cleaning & EDA**: Run `notebooks/clean-and-eda.ipynb` to clean and explore the dataset. This generates the cleaned CSV.
2. **Model Training**: Run `notebooks/model-training.ipynb` to train models and export the scaler/model as `.pkl` files.
3. **Web App (Local)**: Start the Flask app:
   ```bash
   python application.py
   ```
   Open your browser at `http://localhost:5000` and enter feature values to predict FWI.

## Deployment: AWS Elastic Beanstalk
This project is ready for deployment on AWS Elastic Beanstalk as a Python web application.

### Steps:
1. Ensure your project root contains:
   - `application.py` (Flask entry point)
   - `requirements.txt`
   - `.ebextensions/python.config` (for WSGIPath configuration)
2. The `.ebextensions/python.config` file sets the WSGI entry point:
   ```yaml
   option_settings:
     "aws:elasticbeanstalk:container:python":
       WSGIPath: application:application
   ```
3. Zip your project files and deploy via the AWS Elastic Beanstalk console or CLI.
4. Elastic Beanstalk will use `application.py` and the `application` Flask object as the WSGI entry point.

For more details, see the [AWS Elastic Beanstalk Python documentation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create-deploy-python-flask.html).

## Project Structure
```
├── application.py
├── models/
│   ├── ridge_model.pkl
│   └── scaler.pkl
├── notebooks/
│   ├── Algerian_forest_fires_dataset_UPDATE.csv
│   ├── Algerian_forest_fires_dataset_Cleaned.csv
│   ├── clean-and-eda.ipynb
│   └── model-training.ipynb
├── requirements.txt
├── templates/
│   ├── home.html
│   └── index.html
├── README.md
```

## Input Features for Prediction
The web app expects the following features:
- Temperature
- RH (Relative Humidity)
- Ws (Wind speed)
- Rain
- FFMC (Fine Fuel Moisture Code)
- DMC (Duff Moisture Code)
- ISI (Initial Spread Index)
- Classes (0 = Not Fire, 1 = Fire)
- Region (0 = Bejaia, 1 = Sidi-Bel Abbes)

## References
- [UCI Machine Learning Repository: Algerian Forest Fires Dataset](https://archive.ics.uci.edu/ml/datasets/Algerian+Forest+Fires+Dataset+)

## License
This project is for educational and research purposes only.