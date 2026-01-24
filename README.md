# House Price Prediction - Kaggle Competition

A comprehensive machine learning project for predicting house prices using advanced regression techniques. This project follows a modular, agentic AI-inspired structure for better organization and maintainability.

## Project Structure

```
house-prices-advanced-regression-techniques/
├── config/                     # Configuration files
│   ├── model_config.yaml       # Model hyperparameters and settings
│   ├── environment_config.yaml # Environment and path configurations
│   └── logging_config.yaml     # Logging configuration
├── src/                        # Source code
│   ├── core/                   # Core modules
│   │   ├── preprocessor.py     # Data preprocessing
│   │   ├── model.py            # Model definitions
│   │   └── evaluator.py        # Model evaluation
│   └── utils/                  # Utility modules
│       ├── logger.py           # Logging utilities
│       ├── metrics.py          # Metrics tracking
│       └── validator.py        # Data validation
├── data/                       # Data directory
│   ├── training/
│   │   ├── raw/                # Raw datasets (train.csv, test.csv)
│   │   └── processed/          # Processed datasets
│   ├── submissions/            # Submission files
│   ├── logs/                   # Log files and outputs
│   └── checkpoints/            # Model checkpoints
├── notebooks/                  # Jupyter notebooks
│   ├── first_submission.ipynb  # best score comes from this notebook
│   ├── final_notebook.ipynb    # current working notebook
│   └── ...                     # Other analysis notebooks
├── tests/                      # Unit tests
│   ├── test_preprocessor.py
│   └── test_model.py
├── examples/                   # Example scripts
│   ├── train_model.py          # Training example
│   └── predict.py              # Prediction example
├── requirements.txt            # Python dependencies
├── pyproject.toml              # Project configuration
├── Dockerfile                  # Docker configuration
└── README.md                   # This file
```

## Getting Started

### Prerequisites

- Python 3.8 or higher
- pip or conda

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd house-prices-advanced-regression-techniques
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

### Configuration

1. Placed your Kaggle competition files in `data/training/raw/`:
   - `train.csv`
   - `test.csv`
   - `data_description.txt`
   - `sample_submission.csv`

2. Configure model settings in `config/model_config.yaml`

3. Adjust environment paths in `config/environment_config.yaml` if needed

## Usage

### Training a Model

Run the training example script:
```bash
python examples/train_model.py
```

Or use the Jupyter notebook:
```bash
jupyter notebook notebooks/final_notebook.ipynb
```

### Making Predictions

After training, generate predictions:
```bash
python examples/predict.py
```

### Running Tests

```bash
pytest tests/
```

## Key Features

- **Modular Architecture**: Clean separation of concerns with dedicated modules for preprocessing, modeling, and evaluation
- **Configuration Management**: YAML-based configuration for easy hyperparameter tuning
- **Comprehensive Logging**: Structured logging for tracking experiments and debugging
- **Model Evaluation**: Built-in metrics calculation (RMSE, MAE, R²)
- **Data Validation**: Utilities for checking data integrity
- **Ensemble Models**: Support for Ridge Regression, XGBoost, and ensemble combinations

## Model Types

The project supports multiple model types:

1. **Ridge Regression**: Linear regression with L2 regularization
2. **XGBoost**: Gradient boosting regression
3. **Ensemble**: Weighted combination of Ridge and XGBoost

Configure model type and parameters in `config/model_config.yaml`.

## Data Preprocessing

The preprocessing pipeline includes:
- Outlier detection and removal
- Feature scaling (StandardScaler, RobustScaler)
- Missing value handling
- Data validation

## Development

### Project Structure Best Practices

- **Modular Design**: Each module has a single responsibility
- **Configuration-Driven**: Settings are externalized to YAML files
- **Comprehensive Testing**: Unit tests for core functionality
- **Documentation**: Clear docstrings and README

### Adding New Features

1. Add new modules to `src/core/` or `src/utils/`
2. Update configuration files as needed
3. Add tests in `tests/`
4. Update documentation

## Docker Support

Build and run with Docker:

```bash
docker build -t house-price-prediction .
docker run -v $(pwd)/data:/app/data house-price-prediction
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests
5. Submit a pull request

## Acknowledgments

- Kaggle House Prices: Advanced Regression Techniques competition
- Inspired by agentic AI project structure best practices

## Notes

- The main analysis and latest submission code can be found in `notebooks/final_notebook.ipynb`
- Model checkpoints are saved in `data/checkpoints/`
- Submission files are generated in `data/submissions/`
