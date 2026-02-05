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
The solution is built as a modular pipeline consisting of 6 Jupyter Notebooks and 1 Python Dashboard script:

### 1. Data Collection & Wrangling
* **`1_Data_Collection_API.ipynb`**: Automated data extraction from the SpaceX API to build the raw dataset.
* **`2_Data_Wrangling.ipynb`**: Data cleaning (handling missing PayloadMass) and Feature Engineering (One-Hot Encoding for Orbit/Launch Site).

### 2. Exploratory Data Analysis (EDA)
* **`3_EDA_SQL.ipynb`**: Querying the database to find standard success rates and payload ranges using SQL.
* **`4_EDA_Visualization.ipynb`**: Visualizing trends and correlations using Matplotlib & Seaborn.
* **`5_EDA_Folium_Maps.ipynb`**: Geospatial analysis of launch sites to identify "safe zones" and cluster densities.

### 3. Predictive Analysis
* **`6_Machine_Learning.ipynb`**: Training and hyperparameter tuning of 4 classification models (Logistic Regression, SVM, Decision Tree, KNN) to predict landing success.

### 4. Interactive Dashboard
* **`7_spacex_dash_app.py`**: A real-time `Plotly Dash` application allowing users to filter launch data by site and payload mass.

---

## 📊 Model Performance
I benchmarked four classification algorithms to find the optimal "Win Condition" predictor. The **Support Vector Machine (SVM)** achieved perfect accuracy on the test set.

| Model | Accuracy | Notes |
| :--- | :--- | :--- |
| **Support Vector Machine (SVM)** | **100.00%** | **Best performance.** Perfect classification on test data. |
| Logistic Regression | 97.22% | Very strong baseline model. |
| Decision Tree | 94.44% | Highly interpretable, but slightly prone to overfitting. |
| K-Nearest Neighbors (KNN) | 91.67% | Good performance but computationally expensive at scale. |

---

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Data Processing:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn, Folium (Interactive Maps)
* **Machine Learning:** Scikit-learn (GridSearchCV for hyperparameter tuning)
* **Dashboard:** Plotly Dash (Frontend visualization)

---

## 📂 Repository Structure
```bash
├── datasets/                   # Raw and processed .csv data
├── notebooks/                  # Jupyter Notebooks for EDA and Model Training
│   ├── 1_Data_Collection_API.ipynb
│   ├── 2_Data_Wrangling.ipynb
│   ├── 3_EDA_SQL.ipynb
│   ├── 4_EDA_Visualization.ipynb
│   ├── 5_EDA_Folium_Maps.ipynb
│   └── 6_Machine_Learning.ipynb
├── SpaceX_Technical_Slide_Deck.pptx  # Technical Presentation
├── spacex_dash_app.py          # Interactive Dashboard Logic
├── requirements.txt            # Dependencies
└── README.md                   # Documentation
```

## 🚀 How to Run
Prerequisite You must have Python 3.9+ installed.

## Clone the Repository

```Bash
git clone [https://github.com/ryangilbert-github/spacex-launch-predictor.git](https://github.com/ryangilbert-github/spacex-launch-predictor.git)
cd spacex-launch-predictor
```

## Install Dependencies 
This project uses a requirements.txt file to manage libraries.

```Bash
pip install -r requirements.txt
```
Run the Dashboard To launch the interactive analytics dashboard locally:

```Bash
python spacex_dash_app.py
```
The dashboard will open in your browser at http://127.0.0.1:8050/
