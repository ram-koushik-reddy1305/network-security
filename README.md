# Network Security Threat Detection System

An end-to-end machine learning pipeline for detecting network security threats and phishing attempts with real-time prediction capabilities.

## 🚀 Features

- **Real-time Threat Detection**: Machine learning models for network security threat prediction.
- **High-Performance API**: FastAPI-based REST API for serving predictions.
- **Data Management**: MongoDB integration for efficient data storage and retrieval.
- **Experiment Tracking**: MLflow integration for model lifecycle management.
- **Robust Architecture**: Comprehensive logging and custom exception handling.
- **Production Ready**: Scalable modular design for training and deployment pipelines.

## 📋 Prerequisites

- Python 3.8+
- MongoDB Database
- Git

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/ram-koushik-reddy1305/network-security.git
   cd network-security
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv venv
   # Windows
   venv\Scripts\activate
   # Linux/Mac
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```env
   MONGO_DB_URL=your_mongodb_connection_string
   MONGODB_URL_KEY=your_mongodb_connection_string
   ```

5. **Install local package in editable mode**
   ```bash
   pip install -e .
   ```

## 🏗️ Project Structure

```
network-security/
├── src/                    # Source code
│   ├── components/         # Data Ingestion, Validation, Transformation, Model Trainer
│   ├── constant/           # Pipeline configuration constants
│   ├── entity/             # Data entities and configs
│   ├── exception/          # Custom exceptions
│   ├── logging/            # Logging utilities
│   ├── pipeline/           # Training pipeline orchestration
│   └── utils/              # Helper functions & estimators
├── app.py                  # FastAPI web server
├── main.py                 # Pipeline execution script
├── push_data.py            # MongoDB data ingestion script
├── test_monogodb.py        # Database connection verification
├── requirements.txt        # Project dependencies
├── setup.py                # Package configuration
├── Network_data/           # Raw data samples
├── final_model/            # Trained model & preprocessor artifacts
└── templates/              # HTML response templates
```

## 🚀 Usage

### 1. Data Ingestion to MongoDB (Optional)
Push network security dataset to your MongoDB collection:
```bash
python push_data.py
```

### 2. Training the Model
Run the complete training pipeline end-to-end:
```bash
python main.py
```

This executes:
1. **Data Ingestion**: Extracts network security data from MongoDB.
2. **Data Validation**: Validates schema compliance and data quality.
3. **Data Transformation**: Handles feature encoding and missing value imputation.
4. **Model Training**: Evaluates multiple classification models (Random Forest, Decision Tree, Gradient Boosting, etc.) and logs metrics using MLflow.

### 3. Running the FastAPI Web Application
Start the prediction server:
```bash
python app.py
```
Or using Uvicorn directly:
```bash
uvicorn app:app --host 0.0.0.0 --port 8000 --reload
```

Access the interactive API documentation at: `http://localhost:8000/docs`

