Mobile-Screen-time-analysis
This project analyzes screen time usage data from a mobile app. It explores relationships between app usage, notifications, times opened, and day of the week. Additionally, it builds a linear regression model to predict screen time usage based on these factors.

Getting Started
Clone this repository:
Bash
git clone https://github.com/<your_username>/screen_time_usage_analysis.git
Use code with caution.
content_copy
Install required libraries:
Bash
pip install pandas numpy plotly.express plotly.graph_objects scikit-learn matplotlib shap
Use code with caution.
content_copy
Running the Script
Navigate to the project directory:
Bash
cd screen_time_usage_analysis
Use code with caution.
content_copy
Run the script:
Bash
python screentime_analysis.py
Use code with caution.
content_copy
Output
The script generates several visualizations and outputs, including:

Descriptive statistics of the data
Bar charts showing app usage distribution by date, notifications, and times opened
Scatter plot visualizing the relationship between notifications and usage
Evaluation metrics (MAE) for the linear regression model
Visualization of actual vs predicted screen time usage
Confusion matrix for predicted vs actual usage categories
Feature importance analysis
Cross-validation scores and mean CV score
SHAP summary plot for model interpretability
Analysis and Conclusion
The project provides insights into factors affecting screen time usage and demonstrates a basic linear regression model for prediction. Further exploration could involve feature engineering, model selection, and hyperparameter tuning to improve model performance.

Additional Notes
This is a basic example using a linear regression model. More advanced models might be explored for better prediction accuracy.
The code includes comments to explain each step.
