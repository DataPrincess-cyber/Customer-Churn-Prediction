# Customer-Churn-Prediction
### Summary of Steps

1. **Import Libraries**: The necessary libraries were imported, including `pandas`, `matplotlib`, `seaborn`, and various modules from `sklearn` for data processing, modeling, and evaluation.

2. **Load the Dataset**: The dataset was loaded using `pd.read_csv()`, and basic information about the dataset was displayed using methods like `data.info()`, `data.head()`, and `data.describe()`.

3. **Processing Large Datasets in Chunks**: The dataset was read in chunks using `pd.read_csv()` with a `chunksize` parameter. This was useful for handling large datasets that may not fit into memory all at once.

4. **Visual Exploratory Data Analysis (EDA)**:
   - **Boxplots**: Boxplots were created to visualize the relationship between `MonthlyCharges`, `tenure`, and `Churn`.
   - **Countplots**: Countplots were used to explore the distribution of categorical features like `Contract`, `gender`, and `InternetService`.
   - **Heatmap**: Correlation heatmaps were generated for numerical features to understand the relationships between them.
   - **Distribution Plots**: Histograms with kernel density estimates (KDE) were plotted for `tenure`, `MonthlyCharges`, and `TotalCharges`.
   - **Pair Plot**: A pair plot was generated to visualize relationships between numerical features, colored by `Churn`.

5. **Feature Engineering**:
   - **New Feature Creation**: Interaction terms like `MonthlyCharges * tenure` and aggregation features like `TotalServices` were created.
   - **Encoding Categorical Variables**: Categorical features were encoded using one-hot encoding (`pd.get_dummies()`) and label encoding (`LabelEncoder`).
   - **Handling Missing Data**: Missing values were handled using forward fill (`ffill()`), and non-numeric data was converted to numeric.

6. **Data Preparation**:
   - **Data Splitting**: The dataset was split into training and testing sets using `train_test_split()`.
   - **Feature Scaling**: Numerical features were scaled using `StandardScaler` to standardize the data.

7. **Modeling**:
   - **Logistic Regression**: A logistic regression model was trained and evaluated.
   - **Random Forest Classifier**: A random forest classifier was trained and evaluated.
   - **Support Vector Machine (SVM)**: An SVM model was trained and evaluated.

8. **Model Evaluation**: Each model's performance was evaluated using accuracy, precision, recall, and F1 score metrics.

### Challenges Faced

1. **Handling Large Datasets**: Processing large datasets in chunks required additional handling to ensure consistency across chunks. Only a small portion of the dataset was processed in chunks for demonstration purposes.

2. **Encoding Categorical Variables**: The dataset contained multiple categorical features, which required careful encoding. Choosing between one-hot encoding and label encoding was crucial for model performance and interpretability.

3. **Dealing with Missing Data**: Missing data needed to be carefully managed. The `TotalCharges` feature had missing values, which were filled using `fillna()`. Ensuring this didn't introduce bias was important.

4. **Feature Scaling**: Ensuring that the numerical features were appropriately scaled was necessary, especially for models like SVM that are sensitive to feature scales.

5. **Model Selection and Evaluation**: Balancing between different models like logistic regression, random forest, and SVM, and selecting the best model based on evaluation metrics was challenging. Each model had its strengths and weaknesses depending on the nature of the data.

6. **Interpreting Results**: Interpreting the output from the models required a deep understanding of the metrics. For instance, high accuracy does not always imply a good model if the dataset is imbalanced, making precision, recall, and F1 scores more reliable in such cases.
