# SpaceX Launch Success Predictor 🚀

### End-to-End Machine Learning Pipeline for Event Prediction

![Python](https://img.shields.io/badge/Python-3.9-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data_Wrangling-indigo)
![Scikit-learn](https://img.shields.io/badge/Sklearn-Classification-orange)
![Status](https://img.shields.io/badge/Status-Complete-green)

## 🎮 The "Game Engineering" Context
**Why does a Game Engineer care about rockets?**
This project demonstrates the core **Predictive Logic** required for modern Game Analytics.

In this project, I built a pipeline to predict whether a Falcon 9 rocket would successfully land (Win/Loss condition). I use this exact same architecture in **Project Genesis** to model **Boss Fight Outcomes**:
* **SpaceX Inputs:** Payload Mass, Orbit Type, Launch Site.
* **Game Engine Inputs:** Player Gear Score, Class Type, Arena Environment.
* **Shared Logic:** Using Binary Classification (SVM/Decision Trees) to predict a success probability, allowing the AI Director to dynamically adjust difficulty before the encounter begins.

---

## 🏗️ Project Architecture
The solution is built as a modular pipeline:

1.  **Data Mining (REST API):** Automated collection of historical launch data from the SpaceX API.
2.  **Data Wrangling (Pandas/SQL):** Cleaning missing values (PayloadMass) and standardizing categorical features (OrbitType, LaunchSite) using One-Hot Encoding.
3.  **Exploratory Data Analysis (EDA):** Visualizing correlation matrices to identify failure points (e.g., specific orbits had a 0% success rate with high payloads).
4.  **Predictive Modeling:** Training and validating 4 supervised learning models.

---

## 📊 Model Performance
I benchmarked four classification algorithms to find the optimal "Win Condition" predictor:

| Model | Accuracy | F1 Score | Notes |
| :--- | :--- | :--- | :--- |
| **Decision Tree** | **98%** | **0.88** | Best performance on test data. |
| K-Nearest Neighbors | 83% | 0.81 | Good baseline, but computationally expensive at scale. |
| Support Vector Machine (SVM) | 83% | 0.81 | Effective but required significant hyperparameter tuning. |
| Logistic Regression | 82% | 0.80 | - |

---

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Data Processing:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn, Folium (Interactive Maps)
* **Machine Learning:** Scikit-learn (GridSearchCV for hyperparameter tuning)
* **Dashboard:** Plotly Dash (Frontend visualization)

---

## 🚀 How to Run

### Prerequisite
You must have Python 3.9+ installed.

---

### 1. Clone the Repository
```bash
git clone [https://github.com/ryangilbert-github/spacex-launch-predictor.git](https://github.com/ryangilbert-github/spacex-launch-predictor.git)
cd spacex-launch-predictor

## 📂 Repository Structure
```bash
├── datasets/           # Raw and processed .csv data
├── notebooks/          # Jupyter Notebooks for EDA and Model Training
│   ├── 1_Data_Collection_API.ipynb
│   ├── 2_Data_Wrangling.ipynb
│   ├── 3_EDA_SQL.ipynb
│   └── 4_Machine_Learning_Mobile.ipynb
├── spacex_dash_app.py  # Interactive Dashboard Logic
├── requirements.txt    # Dependencies
└── README.md           # Documentation
