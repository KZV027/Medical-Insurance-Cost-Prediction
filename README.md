# Medical-Insurance-Cost-Prediction
This repository provides a Python script and the necessary data for predicting medical insurance costs based on various factors. It utilizes the power of pandas, seaborn, and scikit-learn libraries for data analysis, visualization, and linear regression modeling.


## Requirements
* Python (version 3.x recommended)
* pandas
* seaborn
* matplotlib
* scikit-learn

The project includes a CSV file named ```insurance.csv``` that contains the following columns:

* ```age``` (int):The age of the insured individual.
* ```sex``` (str: 'male' or 'female'): The sex of the insured individual.
* ```bmi``` (float): The body mass index of the insured individual.
* ```smoker``` (str: 'yes' or 'no'): Whether the insured individual smokes or not.
* ```region``` (str: 'southeast', 'southwest', 'northeast', or 'northwest'): The region the insured individual resides in.
* ```charges``` (float): The annual medical insurance cost for the insured individual.

The provided Python script, insurance_cost_prediction.py, is structured as follows:
### 1. Data Import and EDA :
* Reads the ```insurance.csv``` data using pandas.
* Performs exploratory data analysis (EDA) to understand the data's distribution and characteristics. This includes:
* Printing the first few rows (```df.head()```) to get an overview.
* Checking the data shape (```df.shape```) and general information (```df.info()```).
* Examining missing values (```df.isnull().sum()```).
* Summarizing numerical variables (```df.describe()```).
* Visualizing the distribution of age (```sns.distplot(df['age'])```) and sex (```sns.countplot(x='sex', data=df)```).
* Exploring the distribution of BMI (```sns.displot(df['bmi'])```) and the value counts for region (```df['region'].value_counts()```).
* Preprocesses the data by:
* Replacing categorical variables (sex, smoker, region) with numerical representations for compatibility with linear regression.

### 2. Feature and Target Variable Separation:
* Separates the features (```X```) from the target variable (```y```):
* ```X``` includes all columns except ```charges```.
* ```y``` consists of the ```charges``` column.

### 3. Data Splitting :
* Splits the data into training and testing sets using ```train_test_split``` from ```scikit-learn``` with a test size of 20% and a set random state for reproducibility (```random_state=42```).

### 4. Model Training :
* Creates a linear regression model (```reg```) using LinearRegression from scikit-learn.
* Fits the model to the training data (```X_train, y_train```).

### 5. Model Evaluation :
* Evaluates the model's performance using R-squared (```r2_score``` from ```metrics```):
* Calculates R-squared on both the training and testing sets (```r2_train, r2_test```).

### 6. Prediction:
* Provides an example of using the trained model to predict the insurance cost for a new individual with sample data (```input_data```).
* Creates a NumPy array (```input_data_array```) and reshapes it (```input_data_reshape```) for compatibility with the model.
* Makes a prediction (```prediction```) using the model (```reg.predict```).
