# Final Project

**Course:** ENSF 611: Machine Learning for Software Engineers  
**Author:** Steven Duong

## Jupyter Notebook & Submission CSV
In the following folder, you will find the results of the Kaggle competition, along with the project documents: [ENSF 611 - Final Project](https://github.com/StevenD24/ENSF-611-Final-Project/tree/main/ENSF%20611%20-%20Final%20Project)

## Results

I have attached a screenshot below that shows the final score I obtained from Kaggle. The accuracy I obtained was 0.77272.

<img width="1191" alt="image" src="https://user-images.githubusercontent.com/105379503/227672116-16b1968f-08ee-4a96-a436-c380d6cf6cf1.png">

## Code Explanation

Titanic - Machine Learning from Disaster

### 1. Preprocessing Data

Data Cleanup
- Removing unnecessary features such as 'PassengerId', 'Name', 'Ticket', and 'Cabin' from both the training and testing datasets.
- Filling missing values in the 'Age' column with the mean age of the respective dataset.
- Filling missing values in the 'Embarked' column with the mode of the respective dataset.
- Filling the single missing value in the 'Fare' column of the testing dataset with the mean fare of the dataset.
- In this dataset, the 'Sex' column needs to be encoded. We will use a OneHotEncoder to encode the values of male and female.
  
Inspecting the Data
- Displaying the first few rows of the feature matrix (X) and target vector (y) to get an initial sense of the data.
- Printing the dimensions and type of the feature matrix (X) and target vector (y).
- Checking for null values in the datasets and addressing them accordingly.
  
Filling Missing Values
- Filling missing values in the 'Age' column by computing the mean age of the respective dataset and replacing NaN values with the mean age.
- Filling missing values in the 'Embarked' column by computing the mode of the respective dataset and replacing NaN values with the mode.
- Filling the single missing value in the 'Fare' column of the testing dataset by computing the mean fare of the dataset and replacing the NaN value with the mean fare.

Verifying Data Preprocessing
- Using the info() method on both training and testing datasets to ensure that all columns have non-null values and that unnecessary columns have been removed.

### 2. Train Test Split and Cross Validation

Create Training and Test Sets
- Import train_test_split function from scikit-learn.
- Split the dataset X and target vector y into training and test sets using train_test_split() function with specified parameters.
  
Compare Models using Cross-Validation
- Import necessary modules and classifiers.
- Create a list models containing the classifiers: LogisticRegression, SVC, BernoulliNB, RandomForestClassifier, and GradientBoostingClassifier.
- Iterate through the list of models and perform the following tasks:
- Compute the average_precision score using the get_classifier_cv_score() function with 7-fold cross-validation, passing X_train and y_train as arguments.
- Round the scores in the DataFrame to 3 decimal places and print the DataFrame to show the models' training and validation scores.

### 3. Hyperparameter and Re-training the Random Forest Model

Hyperparameter Tuning using Grid Search

- Perform grid search for hyperparameter tuning using GridSearchCV for the RandomForestClassifier.
- Set up a parameter grid with max_depth values ranging from 1 to 10 and max_features values ranging from 0.1 to 0.6.
- Create a GridSearchCV object with the classifier, parameter grid, scoring function set to average_precision, and 10-fold cross-validation.
- Perform the grid search by fitting the GridSearchCV object on X_train and y_train.
  
Grid Search for RandomForestClassifier
- Print the grid search results using the print_grid_search_result() function.
- Plot of Validation Score Heatmap.
- Re-train the best RandomForestClassifier obtained from the grid search on the training dataset X_train and y_train.

### 4. Data Evaluation

Evaluate using Test Data
- Use the retrained model and the test dataset X_test and y_test to evaluate the model's performance.
- Calculate the predicted values using the predict() function.
  
Confusion Matrix and Classification Report
- Plot the confusion matrix using the plot_confusion_matrix() function and the actual and predicted values.
- Print the classification report using the actual and predicted values.
  
Classification Report
- Print the classification report to get precision, recall, and accuracy metrics.
  
Evaluating the Results on Kaggle
- Read the test.csv file and store it in a DataFrame df_test.
- Predict the values for X_testset using the retrained model best_rf and store it in the variable y_pred.
- Create a new DataFrame df_prediction with the PassengerId column from df_test and the predicted Survived values.
- Export the prediction results as a CSV file to submit to Kaggle.

