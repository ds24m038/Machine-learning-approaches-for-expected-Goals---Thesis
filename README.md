# Machine Learning Approaches for Expected Goals (xG)


> **Bachelor Thesis**: Advancing player performance analysis for men's professional football using machine learning approaches for expected goals.

## 📖 Overview

This repository contains the complete implementation of my Bachelor's thesis, which explores **Expected Goals (xG)** modeling using machine learning techniques. The project builds, compares, and evaluates multiple ML models to predict goal-scoring probability from shot events in professional football.

### What is Expected Goals (xG)?

Expected Goals is a probabilistic metric that estimates the likelihood of a shot resulting in a goal. Unlike traditional metrics (goals, shots, possession), xG captures the **quality** of goal-scoring opportunities by analyzing factors such as:

- 📏 **Shot distance** and **angle** to goal
- 👥 **Opponent proximity** (defenders in shooting lane)
- 🧤 **Goalkeeper positioning**
- 🦶 **Body part** used (foot, head)
- 💰 **Player market value** and physical attributes

## 📊 Dataset

The analysis uses publicly available [StatsBomb](https://github.com/statsbomb/open-data) data extracted via their Python API:

### Training Data
Match events from the **2015/16 season** across Europe's top five leagues:
| League | Country |
|--------|---------|
| Bundesliga | 🇩🇪 Germany |
| Premier League | 🏴󠁧󠁢󠁥󠁮󠁧󠁿 England |
| La Liga | 🇪🇸 Spain |
| Serie A | 🇮🇹 Italy |
| Ligue 1 | 🇫🇷 France |

### Evaluation Data
- **FIFA World Cup 2022** data for player performance analysis

## 🔬 Methodology

### Feature Engineering
The project implements comprehensive feature engineering including:

1. **Spatial Features**
   - Distance from shot to goal
   - Angle to goal posts
   - Vertical distance to goalkeeper

2. **Opponent Proximity**
   - Defenders in triangle between shot and goal
   - Number of defenders within pressure radius

3. **Player Attributes** (via Transfermarkt)
   - Strong foot indicator
   - Height threshold (>185cm)
   - Market value at time of shot

4. **Contextual Features**
   - Player position
   - Play pattern (open play, set piece, counter-attack)

### Machine Learning Models

Three classification models are trained and compared:

| Model | Description |
|-------|-------------|
| **Logistic Regression** | Baseline probabilistic model |
| **Random Forest** | Ensemble of decision trees |
| **XGBoost** | Gradient boosting with regularization |

### Evaluation Metrics
- **Log Loss** - Measures probabilistic prediction quality
- **ROC-AUC** - Discrimination ability between goals and non-goals
- **Brier Score** - Calibration of predicted probabilities
- **SHAP Values** - Feature importance analysis

## 🏆 Player Performance Analysis

The trained model is applied to World Cup 2022 data to:

- Identify players with highest expected goals
- Compare xG to actual goals scored
- Analyze over/under-performance relative to xG
- Correlate market value changes with xG metrics

## 📁 Repository Structure

```
.
├── 9_Thesis.ipynb          # Main Jupyter notebook with complete analysis
├── Haghgoo_BachelorThesis.pdf  # Full thesis document
├── LICENSE                 # MIT License
└── README.md               # This file
```

## 🚀 Getting Started

### Prerequisites

```bash
Python 3.8+
Jupyter Notebook / JupyterLab
```

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/Machine-learning-approaches-for-expected-Goals---Thesis.git
   cd Machine-learning-approaches-for-expected-Goals---Thesis
   ```

2. **Install dependencies**
   ```bash
   pip install statsbombpy pandas numpy scikit-learn xgboost shap seaborn matplotlib fuzzywuzzy
   ```

3. **Run the notebook**
   ```bash
   jupyter notebook 9_Thesis.ipynb
   ```

### Required Libraries

| Library | Purpose |
|---------|---------|
| `statsbombpy` | StatsBomb API data extraction |
| `pandas`, `numpy` | Data manipulation |
| `scikit-learn` | ML models and preprocessing |
| `xgboost` | Gradient boosting model |
| `shap` | Model interpretability |
| `seaborn`, `matplotlib` | Visualization |
| `fuzzywuzzy` | Fuzzy string matching (player names) |

## 📈 Key Visualizations

The notebook includes extensive exploratory data analysis:

- 🔷 **Hexagonal shot maps** - Goal locations and miss distribution
- 📊 **Density plots** - Distance and angle distributions
- 🎻 **Violin plots** - Body part analysis
- 📉 **ROC curves** - Model comparison
- 🔥 **SHAP plots** - Feature importance

## 📚 References

1. Rudd, S. (2011). *A Framework for Tactical Analysis and Individual Offensive Production Assessment in Soccer Using Markov Chains*
2. StatsBomb Open Data: [github.com/statsbomb/open-data](https://github.com/statsbomb/open-data)
3. Transfermarkt player data for market values

## 📄 Thesis Document

The complete academic thesis is available in `Haghgoo_BachelorThesis.pdf`, containing:
- Detailed literature review
- Mathematical formulations
- Extended results and discussion
- Full bibliography

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! 

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Sina Haghgoo**

- Vienna University of Economics and Business (WU Wien)

---

<p align="center">
  <i>Built with ⚽ for the football analytics community</i>
</p>
