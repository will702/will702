# Stock Forecasting Engine

Multi-stock time-series forecasting system using XGBoost and technical indicators for Indonesian equity markets.

## Overview

A modular, research-ready forecasting pipeline that generates recursive multi-step predictions for multiple stocks using XGBoost regression and engineered technical indicators. Designed for quantitative analysis of Indonesian stocks (BREN, ITMG, BFIN, etc.) with GridSearchCV hyperparameter tuning and visualization capabilities.

## Problem & Motivation

Stock price prediction requires robust feature engineering, handling of non-linear relationships, and multi-step forecasting capabilities. Traditional linear models fail to capture market dynamics, while deep learning approaches may be overkill for mid-frequency trading signals. XGBoost provides a balance of performance, interpretability, and computational efficiency.

## Architecture

The system follows a modular pipeline architecture:

1. **Data Ingestion**: Historical price data collection and preprocessing
2. **Feature Engineering**: Technical indicators (RSI, MACD, moving averages, volatility measures)
3. **Model Training**: XGBoost regression with GridSearchCV for hyperparameter optimization
4. **Forecasting**: Recursive multi-step prediction with confidence intervals
5. **Visualization**: Charts and performance metrics for model evaluation

Pipeline supports batch processing for multiple stocks and modular replacement of components (feature engineering, model selection, evaluation metrics).

## Key Technical Decisions

- **XGBoost over Deep Learning**: Chosen for interpretability, faster training, and strong performance on tabular time-series data
- **Technical Indicators**: Engineered features capture momentum, trend, and volatility patterns without requiring external data
- **Recursive Forecasting**: Multi-step predictions generated iteratively to maintain temporal dependencies
- **GridSearchCV**: Systematic hyperparameter tuning to optimize model performance across different stocks
- **Modular Design**: Research-ready structure allows easy experimentation with different models and features

## Setup & Usage

### Installation

```bash
pip install xgboost scikit-learn pandas numpy matplotlib
```

### Basic Usage

```python
from forecasting_engine import StockForecaster

# Initialize forecaster
forecaster = StockForecaster(symbol='BREN')

# Load and preprocess data
forecaster.load_data('data/BREN.csv')

# Train model
forecaster.train(n_steps_ahead=5)

# Generate predictions
predictions = forecaster.forecast(steps=5)

# Visualize results
forecaster.plot_predictions()
```

### Hyperparameter Tuning

```python
# Run GridSearchCV
forecaster.tune_hyperparameters(
    param_grid={
        'n_estimators': [100, 200, 300],
        'max_depth': [3, 5, 7],
        'learning_rate': [0.01, 0.1, 0.2]
    }
)
```

## Results / Metrics

- **Model Performance**: Achieved competitive forecasting accuracy on Indonesian stocks
- **Multi-Stock Support**: Modular pipeline enables analysis across multiple equities
- **Research-Ready**: Clean codebase supports experimentation and extension
- **Visualization**: Charts and metrics facilitate model evaluation and interpretation

## Limitations

- Predictions are point estimates without full uncertainty quantification
- Technical indicators may not capture fundamental factors or market regime changes
- Model performance varies by stock and market conditions
- No real-time data integration or live trading capabilities
- Recursive forecasting can accumulate errors over longer horizons

## Roadmap

- Add uncertainty quantification via prediction intervals or probabilistic models
- Integrate fundamental data (earnings, news sentiment) alongside technical indicators
- Implement ensemble methods combining multiple models
- Add real-time data feeds and automated retraining pipelines
- Develop backtesting framework for strategy evaluation
- Extend to additional asset classes (forex, commodities)

## Links

- **GitHub**: <GITHUB_LINK_STOCK_FORECASTING>
- **Documentation**: See `docs/` for methodology and evaluation reports
