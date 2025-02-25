# Online Shopping Purchase Prediction

## 📌 Project Overview
This project aims to analyze customer behavior and predict online shopping purchases using machine learning techniques. The dataset consists of customer attributes such as browsing behavior, session details, and product preferences. The objective is to build a predictive model that helps businesses understand which factors influence purchase decisions.

## 📂 Dataset

The dataset includes the following features:

- **Customer Session Information:** Session duration, number of pages visited, time spent on the website
- **Demographics:** Age, gender, location
- **Product Preferences:** Categories browsed, items added to cart
- **Transaction Details:** Whether a purchase was made

  
## ⚙️ Data Preprocessing

✔ Handling Missing Values:

Filled missing values using mean/median imputation for numerical variables
Used mode imputation for categorical variables
✔ Feature Engineering:

Created new features such as Browsing Intensity Score and Session-to-Purchase Ratio
Applied one-hot encoding for categorical variables
✔ Data Scaling & Transformation:

Standardized numerical variables to improve model performance


## 🏗️ Modeling Approach
We implemented multiple classification models to predict whether a customer will make a purchase:

✅ Logistic Regression<br>
✅ Random Forest Classifier<br>
✅ Gradient Boosting (XGBoost)<br>
✅ Neural Networks<br>

📌 Hyperparameter tuning was done using GridSearchCV.
📌 Evaluation Metrics: Accuracy, Precision, Recall, F1-score, and ROC-AUC score.

## 🔍 Findings & Insights<br>

**🔹 Top Predictors of Purchase:**
- Number of pages visited
- Time spent on the website
- Number of items added to cart

**🔹 Model Performance:**

- Random Forest & XGBoost performed the best, achieving an accuracy of ~85%
Logistic Regression had lower accuracy (~75%) but provided interpretability

**🔹 Business Implications:**<br>
- Optimizing the website experience for high-engagement users can increase conversion rates
Personalized recommendations for high-intent users (who add items to the cart but do not purchase) can improve sales


## 🚀 How to Run the Code
1️⃣ Clone the repository
```sh
git clone <repository-url>
cd Online-Shopping-Prediction
```

2️⃣  Run the Jupyter Notebook or Python script

📌 Open shopping_prediction.ipynb and execute the cells.

## 🔮 Future Improvements<br>

💡 Integrating deep learning models (e.g., LSTMs) for sequential behavior analysis<br>
💡 Implementing real-time recommendation engines<br>
💡 Expanding dataset with more demographic and behavioral features<br>

## 🤝 Contributors

👨‍💻 Vignesh Kumar(https://github.com/vigneshkr13) | 📧 ess.vigneshkr@gmail.com

## 📜 License
This project is licensed under the MIT License.
