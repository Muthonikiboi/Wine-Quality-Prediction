# BUSINESS UNDERSTANDING
## 1. Problem Statement
"A wine manufacturing company wants to automate its quality control process to help in reducing manual errors and increase consistency in wine grading in terms of quality. They aim to develop a predictive model that classifies wines into 'high quality' or 'low quality' sections based on provided features and chemical properties to optimize production, marketing and pricing strategies."

## 2. OBJECTIVES
1. Identify the all the main chemical properties that influence wine quality.

2. Build a classification model to categorize wine into quality labels (0:low or 1:high)

3. Determine the role wine type (in red or white) plays in wine quality.

4. Compare different model performances

# DATA UNDERSTANDING
- The dataset is a kaggle dataset obtained from wine data with type white and red.
- The dataset has 6497 rows and 13 columns.
- The data contains no missing values.

# DATA PREPARATION PROCESSING
- Binary Encoding
- Adding new imporntant features
  ## Explanatory Data Analysis
  1. Understanding relationship between other features and our target `quality`.
     ![image](https://github.com/user-attachments/assets/7777467e-9695-4264-86f3-bf40b053ac09)

     Correlation coeffficients range from `-1` to `1` where:
    `+1` strong positive correlation(an increase in one leads to an increase in the other)
    `-1` strong negative correlation(as one increases the other decreases)
    `0` There is no correlation
    
    Our main concern is how features relate to `quality`.
    
    From the matrx above we conclude the features with the highest correlation to qualitya are `alcohol` with `0.44`(positive correlation) and `volatile acidity` with `-0.27` (negative correlation)

   2.Distribution of wine in terms of quality.
  
   ![image](https://github.com/user-attachments/assets/791966d0-210f-4e65-8f52-28778312a243)

   The image shows the relationship between quality and alcohol(strongest correlation)

    - Wines with higher alcohol tent to receive higher quality rates
    - quality levels at 5,6,7 are the most frequent
      
  3.Identify outliers and distribution in both qualities
  
  ![image](https://github.com/user-attachments/assets/02241f19-1ae2-4739-8657-195e6306041d)
  
  The first diagram shows us that:
  - Maximun wine count ranges at around 5 and 6 ..Clarifies that wine color does not affect the quality as they have their means around the same point.
  - Visible that white tends to have more outliers with very high quality.
  
  The second diagram:
  - Lower wines that are <7 are produces more as they have a higher count at both low and high levels than the high quality wines
  - More white wines are produced than red wines.
 
# MODELING
in Modeling used:
-Multi Linear Regression
-Logistic Regression
-Decision Tree
-Gradient Boosting Classifier
##### Model Comparison
![image](https://github.com/user-attachments/assets/25bf861a-680e-437d-bbd3-bb686d4db08d)

From this table we can conclude that the Decision tree provided the best model accross all metrics.

##### Feature Selection
![image](https://github.com/user-attachments/assets/c5839fc2-9adc-4e4c-89f3-f947fa3ddf09)
The two images above indicate to us that `alcohol` is the feature tha affects the data quality most.

# Recommendation
1. Perform external validations using other datasets 
2. One can enhance quality lables by adding a medium class.
3. Reclass or reweight to handle the class imbalance orrectly

# Limitation
1. Dataset Imbalance on Fewer higher qality wines and more low quality wines create a class imbalance.
2. No external test data was used to test the model

# Conclusion
1. Alcohol and volatile acidity play a crucial role in predicting wine quality.This shows that they play a great role in the quality of the data.
2. Decision tree provide the most balanced classification.
3. Wine type should be included as it has moderate effect on quality.
