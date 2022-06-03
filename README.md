# Garments Industry Employee Productivity

### Tijesunimi Odebode

**Description:**

This project involves using machine learning to predict garment workers that met their productivity goals based on certain features in the garment manufacturing process. The project is important because decision makers in the garment industry could use the analysis and prediction of employee productivity to improve the overall production of garments and ultimately improve company revenue.

**Data Source:**

The data used in this project was retrieved from the UCI Machine Learning Repository website: https://archive.ics.uci.edu/ml/datasets/Productivity+Prediction+of+Garment+Employees#

**The Code:**

a. Loading and verifying data - In this part, the needed packages were imported, and the garment industry employee productivity data was loaded and verified

b. Data Cleaning - In this part, several steps were carried out to clean the data. 

•	Missing values and inconsistent categories of data were addressed. For "wip" column, the median weight was determined, and that median was inserted in the cells with missing value. ‘wip’ is short for “work in progress.” It represents the number of unfinished items for products.

•	Feature engineering was applied to the ‘date’ column and new columns were created for the numeric days and numeric months from the dates.

•	Duplicates in the data were checked for and there were no duplicates. 

•	Rows with actual productivity of employees (column title is actual_productivity) greater than 1 were deleted from the data set. According to the data set information on the UCI website, actual productivity should be between 0 and 1.

•	An inconsistent category of data in the ‘department’ column was fixed

•	Outliers were identified and kept

•	In the dataset, there is a column titled 'targeted_productivity.' This column represents the targeted productivity (a number between 0 and 1) set by the Authority for each team for each day. A new column titled 'met_goal' was created for employee teams that met their target productivity goal. The column had either a ‘Yes’ or ‘No.’ ‘Yes’ for those who met their goals and ‘No’ for those who did not meet their goals. The 'actual_productivity' column was dropped

•	The string names of the new column ‘met_goal’ were converted to numeric values of 0 and 1. ‘0’ for ‘No’ and ‘1’ for ‘Yes.’

•	A validation split was performed

•	Numerical features were scaled and nominal categorical features were one-hot encoded.

**Univariate and multivariate visualizations:**

In this section, barcharts, histograms, boxplots and a heat map were used for explanatory and exploratory visualizations. The following visualizations were shown:

•	Barchart of 'department' column. The count of each department was plotted

•	Compare actual productivity for each department

•	Compare actual productivity for each department for each day of the week.

•	Histogram of 'targeted_productivity' column. The 'targeted_productivity' column represents targeted productivity set by the authority for each team for each day.

•	Histogram of 'actual_productivity' column. The 'actual_productivity' column represents the actual % of productivity that was delivered by the workers.

The following are two examples of visualizations that were made. The first is a comparison of the actual productivity of employees for each department per week day. The second is a correlation heatmap for the dataset.

![image](https://user-images.githubusercontent.com/97941938/162676304-ebba09c0-1fd6-4448-b948-f9451a651997.png)

Table 1: Actual productivity of employees for each department per weekday

![image](https://user-images.githubusercontent.com/97941938/162676415-8c78dc69-8772-46f8-91e8-348f0bbf49ee.png)

Table 2: Correlation heatmap of the garment employee productivity dataset.

**Models:**

In this section, the following tasks were carried out:

a. A logistic regression model was built to predict employee teams that met their productivity goals. The performance of the model was evaluated based on accuracy. Other metrics were also considered such as precision, recall, and f1-score. The logistic regression model was also tuned to optimize the model performance.

b. A KNN model was built to predict employee teams that met their productivity goals. The performance of the model was evaluated based on accuracy. Other metrics were also considered such as precision, recall, and f1-score. The KNN model was also tuned to optimize the model performance.

c. A Random Forest model was built to predict employee teams that met their productivity goals. The performance of the model was evaluated based on accuracy. Other metrics were also considered such as precision, recall, and f1-score. The Random Forest model was also tuned to optimize the model performance.

d. The model to implement was determined. A justification was provided for the recommendation.

**Findings:**

•	All the models had some level of overfitting. The accuracy scores for all models were not that great but were not terrible either.

•	I have chosen the optimized KNN model because it's the model with the least overfitting. It's training accuracy score was 0.8207 and its testing accuracy score was 0.7517. It's testing score is also not significantly different from the testing scores of the optimized logistic regression model and optimized Random Forest model.

•	Also, based on the confusion matrices, the KNN model was better at identifying employee teams that met or exceeded their target productivity, which is important for this problem. The KNN model was able to successfully classify 90% of the samples in our test set that were class 1 ('Yes' representing employee teams that met or exceeded their target productivity).

•	As a result of the above reasons, I would choose the KNN model.

  **Video Presentation:**

The following link contains a presentation I gave about this project. I assumed I was talking to a technical audience in the presentation, so the presentation has exploratory visuals and codes: https://drive.google.com/file/d/1YFUMF7p563BMlnzy8ZiE3ma4qXXK4E4i/view?usp=sharing
