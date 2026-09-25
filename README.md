# Stock Return Prediction Using Machine Learning

A machine learning project that investigates whether technical indicators derived from historical stock market data can predict the direction of a stock's future 5-day return.

## Project Objective

The objective of this project is to build and evaluate supervised machine learning models that classify whether a stock will have a positive or non-positive return over the following 5 trading days.

The project uses historical stock price and volume data and derives technical indicators as machine learning features.

## Target Variable

The prediction target is based on the stock's future 5-day return:

- `1` → future 5-day return > 0
- `0` → future 5-day return ≤ 0

The target is created using future prices while ensuring that future information is not included in the input features.

## Features

The current feature set contains:

- `return_5d`
- `price_vs_MA50`
- `price_vs_MA200`
- `RSI`
- `volume_change_20d`
- `MACD`
- `MACD_signal`
- `MACD_hist`
- `BB_position`
- `ATR_pct`

### Technical Indicators

#### 5-Day Return

Measures the percentage change in closing price over the previous 5 trading sessions.

#### Price vs MA50

Measures how far the current price is from its 50-day moving average.

#### Price vs MA200

Measures how far the current price is from its 200-day moving average.

#### RSI

Relative Strength Index, used to measure recent price momentum.

#### Volume Change

Measures the change in trading volume relative to the volume 20 trading days earlier.

#### MACD

Moving Average Convergence Divergence, a momentum and trend-following indicator.

#### Bollinger Band Position

Measures where the current price lies relative to the Bollinger Band range.

#### ATR

Average True Range, used as a measure of price volatility.

## Data Processing Pipeline

The project follows this general pipeline:

Raw historical market data

↓

Long-format stock price dataset

↓

Technical indicator calculation

↓

Future 5-day return calculation

↓

Binary target creation

↓

Feature selection

↓

Train/test split

↓

Feature scaling where required

↓

Machine learning models

↓

Model evaluation

## Models Tested

The current project evaluates:

1. Logistic Regression
2. Random Forest
3. Gradient Boosting
4. Support Vector Machine
5. K-Nearest Neighbors

## Initial Results

Initial test-set results:

| Model | Accuracy | ROC-AUC |
|---|---:|---:|
| Logistic Regression | 50.16% | 0.492 |
| Random Forest | 50.10% | 0.515 |
| Gradient Boosting | 50.84% | 0.519 |
| SVM | 49.92% | 0.495 |
| KNN | 49.46% | 0.500 |

The current results indicate that the technical indicators used in the baseline models provide only a weak directional signal for the next 5 trading days.

Gradient Boosting currently has the highest ROC-AUC among the tested models, but its ROC-AUC remains close to the 0.50 random baseline.

These results should therefore be treated as a baseline rather than evidence of a strong predictive trading signal.

## Evaluation Metrics

The models are evaluated using:

### Accuracy

The percentage of predictions that are correct.

### Precision

Among observations predicted as a particular class, the proportion that actually belongs to that class.

### Recall

The proportion of actual observations belonging to a class that the model correctly identifies.

### F1 Score

The harmonic mean of precision and recall.

### ROC-AUC

Measures how well the model separates the two classes based on its prediction scores/probabilities.

A ROC-AUC of:

- `1.0` → perfect separation
- `0.5` → approximately random
- `< 0.5` → ranking worse than random

## Project Status

Current stage:

- [x] Historical price data preparation
- [x] Long-format dataset creation
- [x] Technical indicators
- [x] Future 5-day return
- [x] Binary target
- [x] Train/test split
- [x] Feature scaling
- [x] Logistic Regression
- [x] Random Forest
- [x] Gradient Boosting
- [x] SVM
- [x] KNN
- [ ] Naive Bayes
- [ ] Hyperparameter tuning
- [ ] Time-series cross-validation
- [ ] Feature analysis
- [ ] Probability calibration
- [ ] Trading strategy/backtest
- [ ] Final model comparison

## Important Note

This project is an experimental machine learning study and is not intended to provide investment advice or guaranteed trading predictions.

The current results are baseline results obtained from the current feature set and evaluation methodology. Further validation is required before drawing conclusions about real-world trading performance.

## Future Improvements

Planned improvements include:

- Time-series cross-validation
- Hyperparameter optimization
- Feature selection
- Additional technical indicators
- Alternative prediction horizons
- Probability calibration
- Threshold optimization
- Transaction costs
- Slippage
- Portfolio-level backtesting
- Risk-adjusted performance metrics
- Comparison with simple trading benchmarks