# Wine Quality Prediction ML App

This is an End-to-End Machine Learning project designed to predict wine quality based on various chemical properties (such as acidity, residual sugar, chlorides, etc.). The project includes a complete pipeline from data ingestion to model deployment, and features a user-friendly Flask web interface for making real-time predictions.

## How the Work Flows

1. **Data Ingestion**: Downloads and extracts the dataset from a remote source.
2. **Data Validation**: Checks the dataset columns and types against a predefined schema.
3. **Data Transformation**: Prepares and splits the dataset for training and testing.
4. **Model Trainer**: Trains an ElasticNet regression model using hyperparameter configuration.
5. **Model Evaluation**: Evaluates the trained model using MLflow, logging metrics such as RMSE, MAE, and R2 score.
6. **Web App**: A Flask application serves the trained model for inference via a web interface.

## Technologies Defined

- **Python**: Core programming language.
- **Flask**: Web framework for the user interface and API.
- **Scikit-Learn**: Machine learning library for training the ElasticNet model.
- **Pandas & NumPy**: Data manipulation and numerical operations.
- **MLflow & DagsHub**: For experiment tracking, model registry, and logging.
- **Docker**: Containerization of the application.
- **AWS (EC2 & ECR)**: Cloud infrastructure for deploying the Docker container.
- **GitHub Actions**: CI/CD pipeline for automated testing and deployment.

## How to Use the Project

### 1. Clone the repository
```bash
git clone https://github.com/tyson0911/ML-Flow.git
cd ML-Flow
```

### 2. Create a conda environment
```bash
conda create -n mlproj python=3.8 -y
conda activate mlproj
```

### 3. Install the requirements
```bash
pip install -r requirements.txt
```

### 4. Run the Application
```bash
python app.py
```
After running this command, open your local host and port (typically `http://localhost:8080` or `http://0.0.0.0:8080`) in your web browser.

## MLflow Tracking

To enable MLflow tracking with DagsHub, export your credentials as environment variables before running the pipeline or the application:

```bash
export MLFLOW_TRACKING_URI=https://dagshub.com/tyson0911/ML-Flow.mlflow
export MLFLOW_TRACKING_USERNAME=tyson0911 
export MLFLOW_TRACKING_PASSWORD=<your-dagshub-token>
```

## Dataset Features

The ElasticNet model makes predictions using the following physicochemical features of wine:
- Fixed Acidity
- Volatile Acidity
- Citric Acid
- Residual Sugar
- Chlorides
- Free Sulfur Dioxide
- Total Sulfur Dioxide
- Density
- pH
- Sulphates
- Alcohol

## Project Structure

- `src/mlProject/`: Core module containing all the pipeline components.
- `config/`: Configuration files mapping the data sources, models, and artifacts.
- `research/`: Experimental Jupyter notebooks used during the prototyping phase.
- `templates/` & `static/`: HTML and CSS for the Flask web application.
- `app.py`: The Flask server entry point.
- `main.py`: The executable script to trigger the entire training pipeline end-to-end.

---

© Copyright 2026, Aryan Agrawal. All rights reserved.
