# Customer-Churn-Prediction
### Summary of Steps

Below is a summary of the steps involved:

1. **Import Libraries:** Import the required libraries needed for this task: pandas, matplotlib, seaborn, numpy, and scikit-learn.

2. **Load and Explore Data:**
   - Load the dataset from a CSV file.
   - Display basic information, the first few rows, and a statistical summary of the dataset.
   - Process large datasets in chunks for more efficient handling.

3. **Data Visualization:**
   - Visualize relationships between features such as MonthlyCharges, tenure, Contract, and Churn using box plots and count plots.
   - Generate a heatmap to show correlations between numerical features.
   - Create distribution plots for numerical features (tenure, MonthlyCharges, TotalCharges).
   - Explore categorical features using count plots and box plots.

4. **Data Preprocessing:**
   - Drop irrelevant columns (e.g., customerID).
   - Convert TotalCharges to numeric, handling errors by coercing them to NaN and filling with 0.
   - Identify and drop non-numeric columns for correlation analysis.
   - Encode categorical features using one-hot encoding.
   - Create new features, such as interaction terms (MonthlyCharges * tenure) and aggregate features (e.g., TotalServices).

5. **Model Preparation:**
   - Split the data into features (X) and the target variable (y), and further into training and testing sets.
   - Handle missing values by filling them with the mean of each feature.
   - Scale numerical features using StandardScaler.

6. **Model Training and Evaluation:**
   - Train three models: Logistic Regression, Random Forest, and Support Vector Machine (SVM).
   - Evaluate each model on the test set using metrics such as accuracy, precision, recall, and F1 score.
   - Print the performance metrics for each model to compare their effectiveness.

### Challenges Faced

1. **Handling Large Datasets**: Processing large datasets in chunks required additional handling to ensure consistency across chunks. Only a small portion of the dataset was processed in chunks for demonstration purposes.

2. **Encoding Categorical Variables**: The dataset contained multiple categorical features, which required careful encoding. Choosing between one-hot encoding and label encoding was crucial for model performance and interpretability.

3. **Dealing with Missing Data**: Missing data needed to be carefully managed. The `TotalCharges` feature had missing values, which were filled using `fillna()`. Ensuring this didn't introduce bias was important.

4. **Feature Scaling**: Ensuring that the numerical features were appropriately scaled was necessary, especially for models like SVM that are sensitive to feature scales.

5. **Model Selection and Evaluation**: Balancing between different models like logistic regression, random forest, and SVM, and selecting the best model based on evaluation metrics was challenging. Each model had its strengths and weaknesses depending on the nature of the data.

6. **Interpreting Results**: Interpreting the output from the models required a deep understanding of the metrics. For instance, high accuracy does not always imply a good model if the dataset is imbalanced, making precision, recall, and F1 scores more reliable in such cases.
