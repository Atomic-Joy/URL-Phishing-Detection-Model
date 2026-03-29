# URL Phishing Detection Model

## 🛡️ Overview
This is a final year project focused on detecting phishing URLs using Machine Learning techniques. The Internet has become an integral part of our lives, but it has also brought challenges such as phishing attacks, where malicious actors use fraudulent sites to steal sensitive information. This project develops a robust pipeline to systematically detect and classify these URLs based on their lexical properties and structural attributes.

## 📊 Dataset
The dataset utilized for this project is sourced from [Mendeley Data](https://data.mendeley.com/datasets/6tm2d6sz7p/1).
- **Total Instances:** 247,950 
- **Legitimate URLs:** 119,409 (Class `0`)
- **Phishing URLs:** 128,541 (Class `1`)
- **Total Features:** 41 extracted features + 1 target variable. 

The dataset is highly balanced, which allows for stable and reliable model training without severe class imbalance issues.

## 🔍 Key URL Features Extracted
The detection relies entirely on 41 distinct URL-based features, making the detection process lightweight, fast, and proactive (no need to visit or load page content). Some of the core feature categories include:
- **Length-Based:** `url_length`, `domain_length`, `path_length`
- **Character Counts:** Counts of special characters (`@`, `?`, `-`, `=`, `_`, etc.)
- **Structural:** `number_of_subdomains`, presence of repetitive digits, IP address usage
- **Complexity:** `entropy_of_url` & `entropy_of_domain`

## 🤖 Machine Learning Models
To achieve high accuracy and robustness, several machine learning algorithms were implemented and evaluated:
- **Random Forest:** Used for its powerful ensemble approach and to clearly derive **Feature Importances** (identifying which specific structural parts of a URL are the biggest red flags).
- **K-Nearest Neighbors (KNN):** Implemented to group and find spatial similarities between established phishing patterns and newly observed URLs.
- **CatBoost:** Leveraged for advanced gradient boosting to handle complex, non-linear relationships efficiently.

## 📈 Exploratory Data Analysis & Visualizations
Comprehensive data analysis forms the backbone of this project. Various artifacts generated include:
- **Feature Importance (Random Forest):** Identifies the top URL indicators that signal a phishing attempt.
- **Histograms & Distributions:** Analyzes how specific features (like URL length or entropy) differ between the phishing and legitimate classes.
- **Pairplots & Correlations:** Used to identify highly correlated variables and understand relationship dynamics.
- **Class Balance (Pie Charts):** Verifying the symmetric nature of the target variable.

## 📂 Project Structure
```text
├── Dataset.csv                          # The main dataset containing 247k+ URL features
├── ModelTraining.ipynb                  # Central Jupyter Notebook containing EDA, preprocessing, training, and evaluation
├── histograms/                          # Directory containing feature distributions
├── histograms_with_counts/              # Directory with detailed distribution counts
├── catboost_info/                       # Metadata and training logs from CatBoost model
├── *.png                                # Generated visual plots (Feature Importance, KNN Accuracy, etc.)
└── README.md                            # Project documentation
```

## 🚀 How to Run
1. Ensure you have Python installed along with Jupyter Notebook or an environment like Anaconda.
2. Clone or download this project directory.
3. Install the required data science dependencies:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn catboost
   ```
4. Launch Jupyter Notebook and open `ModelTraining.ipynb`.
5. Execute the cells sequentially to run the end-to-end pipeline, view EDA visualizations, and re-train the models.
