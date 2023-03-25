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

Preprocessing Data
- Removing unnecessary features such as 'PassengerId', 'Name', 'Ticket', and 'Cabin' from both the training and testing datasets.
- Filling missing values in the 'Age' column with the mean age of the respective dataset.
- Filling missing values in the 'Embarked' column with the mode of the respective dataset.
- Filling the single missing value in the 'Fare' column of the testing dataset with the mean fare of the dataset.
  
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
