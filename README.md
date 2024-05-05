<h1 align="center" id="title">Mobile-Screen-time-analysis</h1>

<p id="description">This project analyzes screen time usage data from a mobile app. It explores relationships between app usage notifications times opened and day of the week. Additionally it builds a linear regression model to predict screen time usage based on these factors.</p>

<h2>🛠️ Installation Steps:</h2>

<p>1. Clone this repository:</p>

```
git clone https://github.com//screen_time_usage_analysis.git
```

<p>2. Install required libraries:</p>

```
pip install pandas numpy plotly.express plotly.graph_objects scikit-learn matplotlib shap
```

<p>3. Running the Script Navigate to the project directory:</p>

```
cd screen_time_usage_analysis
```

<p>4. Run the script:</p>

```
python screentime_analysis.py
```

**Output**
The script generates several visualizations and outputs to understand screen time usage patterns:

**Descriptive statistics:** Summarizes the data (e.g., mean, standard deviation) for app usage, notifications, times opened, etc.
Bar charts: Visualize the distribution of app usage across different factors:
Date: Shows how usage varies by day.
Notifications: Illustrates the relationship between notifications received and usage.
Times opened: Depicts how usage changes based on how many times the app is opened.
Scatter plot: Explores the correlation between the number of notifications and screen time usage.
Evaluation metrics (MAE): Measures the absolute difference between actual and predicted usage for the linear regression model.
Visualization: Compares actual screen time usage with the model's predictions.
Confusion matrix: Shows how well the model classified usage categories (e.g., low, moderate, high).
Feature importance analysis: Identifies which factors (day of week, notifications, times opened) have the most significant influence on predicting usage.
Cross-validation scores and mean CV score: Evaluates the model's performance across different data splits.
SHAP summary plot: Provides insights into how each feature contributes to individual predictions.

**Analysis and Conclusion**
The project provides insights into factors affecting screen time usage and demonstrates a basic linear regression model for prediction. Further exploration could involve feature engineering, model selection, and hyperparameter tuning to improve model performance.

**Additional Notes**
This is a basic example using a linear regression model. More advanced models might be explored for better prediction accuracy.
The code includes comments to explain each step.
