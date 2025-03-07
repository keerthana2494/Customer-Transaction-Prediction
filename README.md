# Customer-Transaction-Prediction

# **1. Introduction**
- In the financial sector, predicting customer transactions accurately is crucial for effective decision-making and resource allocation. This report presents a comprehensive analysis of a dataset containing 200,000 entries and 202 columns, aiming to build a predictive model to help banks identify which customers are likely to make future transactions. The key objectives of this analysis are:

        1. To perform detailed Exploratory Data Analysis (EDA) to understand data distribution
           and identify potential preprocessing requirements.
        2. To evaluate and compare multiple predictive models for transaction prediction.
        3. To select the best-performing model based on accuracy, precision, recall, and
           F1-score.

  #  2. Data Overview
- Total Entries: 200,000
- Total Features: 202 (including one identifier ID_code and one object column)
- Data Types:
   - Float64: 200 columns
   - Int64: 1 column
   - Object: 1 column (likely categorical or identifier)
 
# 3. Data Preprocessing
**3.1 Handling Missing Values**
- Observation:
     - No missing values detected in the dataset. No imputation was required.

**3.2 Outlier Management**
- Observation:
     -Outliers were present but not removed due to the normal distribution of most features.   Instead, RobustScaler was applied to mitigate their impact.

**3.3 Data Distribution Analysis**
- Key Findings:
- Most features follow a normal (Gaussian) distribution with:
     - Mean: 6.5 to 7.0
     - Standard Deviation: 9 to 10
  - Feature Transformation: Not required as data closely follows a normal distribution.
- Visualization Insights:
   - Histograms and density plots confirmed the Gaussian distribution of most features.
   - PCA Analysis: Reduced features from 200 to 175 with minimal variance loss.

**3.4 Handling Class Imbalance**
- Original Distribution:
   - Class 0: 179,902
   - Class 1: 20,098
- Balanced Distribution:
   - Class 0: 179,902
   - Class 1: 179,902 (achieved via oversampling)

**3.5 Correlation Analysis**
- Heatmap Analysis:
    - No significant correlation observed between features.
- Conclusion:
   - No need for feature removal based on correlation.
     
# 4. Model Building and Evaluation
**4.1 Models Used**
   1. Logistic Regression
   2. Artificial Neural Network (MLP Classifier)
   3. XGBoost Classifier

**4.2 Logistic Regression**
- Training Accuracy: 83.51%
- Testing Accuracy: 83.61%
- Classification Report:
    - Precision: 0.83
    - Recall: 0.84
    - F1-Score: 0.84
- Observation:
    - Performed modestly but lacked the ability to capture complex patterns.

**4.3 MLP Classifier (ANN)**
- Training Accuracy: 93.76%
- Testing Accuracy: 90.51%
- Classification Report:
    - Precision: 0.90
    - Recall: 0.91
    - F1-Score: 0.91
- Observation:
    - Performed well with high accuracy and F1-score but had longer training times.

**4.4 XGBoost Classifier**
- Training Accuracy: 93.78%
- Testing Accuracy: 90.60%
- Classification Report:
    - Precision: 0.90
    - Recall: 0.91
    - F1-Score: 0.91
- Observation:
    - Best performance among the models with balanced precision, recall, and F1-score.

 **5. Model Comparison**

| **Model**                     | **Training Accuracy (%)** | **Testing Accuracy (%)** | **F1-Score** |
|-------------------------------|---------------------------|---------------------------|---------------|
| Logistic Regression           | 83.51                      | 83.61                      | 0.84          |
| MLP Classifier (ANN)          | 93.76                      | 90.51                      | 0.91          |
| XGBoost Classifier            | 93.78                      | 90.60                      | 0.91          |




**Key Insight:**

 -  XGBoost Classifier showed the best balance between training and testing accuracy, making it the most reliable model for predicting customer transactions.

# **6. Conclusion**
- Best Model:
    - The XGBoost Classifier is recommended due to its superior testing accuracy (90.60%) and balanced performance metrics (precision, recall, F1-score).
- Data Insights:
   - Most features are normally distributed with no significant correlation, allowing effective scaling and model performance.
- Future Work:
    - Explore optimized hyperparameter tuning using techniques like Grid Search with Cross-Validation or Bayesian Optimization to further improve model accuracy.
    - Consider distributed computing or cloud-based solutions to handle large datasets efficiently.             
