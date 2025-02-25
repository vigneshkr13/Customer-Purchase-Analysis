
# Predicting Whether An Online Shopper Purchases An Item Based On Their Behaviour  

## Project Overview  
This project aims to predict whether an online shopper will make a purchase based on their browsing behavior. The dataset used for this study is the **"Online Shoppers Purchasing Intention Dataset"**, obtained from the UCI Machine Learning Repository. Two classification algorithms, **K-Nearest Neighbours (KNN)** and **Decision Tree**, are implemented and compared to evaluate their predictive capabilities.  

## Dataset Description  
- **Total Instances**: 12,330 (after cleaning: 12,205)  
- **Total Attributes**: 18 (Numerical & Categorical)  
- **Target Variable**: `Revenue` (Binary: 1 if purchase was made, 0 otherwise)  
- **Key Features**:  
  - `Administrative`, `Informational`, `ProductRelated` (Number of pages visited)  
  - `BounceRates`, `ExitRates`, `PageValues` (Session engagement metrics)  
  - `Month`, `VisitorType`, `SpecialDay` (Categorical attributes related to time and user type)  

## Methodology  
### 1. **Data Preprocessing**  
- Checked for **missing values** (None found).  
- **Removed duplicate rows** (125 duplicates removed).  
- **One-hot encoding** applied for categorical attributes (`Month`, `VisitorType`).  
- **Feature scaling** applied where necessary.  

### 2. **Exploratory Data Analysis (EDA)**  
- **Individual column analysis** (Pie charts, bar graphs, histograms)  
- **Pairwise feature relationships** (Heatmaps, scatter plots)  
- **Key Findings**:  
  - **PageValues** has the highest correlation with **Revenue**.  
  - **BounceRates and ExitRates** are highly correlated.  
  - **Shopping on weekends does not significantly affect purchases**.  

### 3. **Modeling & Evaluation**  
#### **K-Nearest Neighbours (KNN)**  
- **Initial accuracy**: **86%** with `k=3`.  
- **Hyperparameter tuning** using the **greedy method** for `k`, weights, and distance metric.  
  - Best parameters: `k=5`, `weights='distance'`, `p=1`.  
  - Accuracy improved to **87%**.  
- **Feature selection** using **Hill Climbing**.  
  - Selected features: `Region`, `PageValues`, `VisitorType`, `Administrative`, `SpecialDay`, `Month`.  
  - Retrained accuracy: **88%**.  

#### **Decision Tree Classifier**  
- **Initial accuracy**: **91%**.  
- **Hyperparameter tuning** using **GridSearchCV**.  
  - Found optimal parameters: `max_depth=5`, `min_samples_split=2`, `criterion='gini'`.  
  - Accuracy remained at **91%**.  
- **Feature importance analysis** showed that `PageValues` was the most significant predictor.  

### 4. **Results & Comparison**  
| Model | Initial Accuracy | Tuned Accuracy | Feature Selection | Final Accuracy |  
|--------|-----------------|---------------|-------------------|---------------|  
| KNN | 86% | 87% | Yes (Hill Climbing) | **88%** |  
| Decision Tree | 91% | 91% | Yes (Feature Importance) | **91%** |  

### 5. **Key Insights**  
- Decision Tree outperformed KNN, achieving higher accuracy due to its ability to handle **non-linear relationships**.  
- `PageValues`, `ProductRelated_Duration`, `BounceRates`, and `ExitRates` are the **most significant predictors** of purchases.  
- Businesses should **focus on optimizing product page duration, reducing bounce rates, and improving page values** to increase conversions.  

## How to Run the Code  
### **Prerequisites**  
Ensure you have the following Python libraries installed:  
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### **Execution Steps**  
1. **Clone the Repository**  
   ```bash
   git clone https://github.com/your-repo-url
   cd online-shopper-prediction
   ```
2. **Run the Python script**  
   ```bash
   python shopper_prediction.py
   ```
3. **Check the results** (accuracy, confusion matrix, and feature importance).  

## File Structure  
```
📂 Online-Shopper-Prediction  
│── 📜 README.md  # This file  
│── 📜 shopper_prediction.py  # Main script for modeling  
│── 📜 online_shoppers_intention.csv  # Dataset  
│── 📜 requirements.txt  # Dependencies  
│── 📂 results/  # Output graphs and evaluation metrics  
```

## References  
- Sakar, C. O., & Kastro, O. (2018). Online Shoppers Purchasing Intention Dataset. UCI Machine Learning Repository.  
- Verma, R. (2021). One-hot encoding for categorical variables.  

