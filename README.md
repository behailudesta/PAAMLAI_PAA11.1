

## Professional Certificate in Machine Learning and Artificial Intelligence.
---

### Practical Application Assignment 11.1
## What drives the price of a car?
### Overview
In this application, you will explore a dataset from kaggle. The original dataset contained information on 3 million used cars. The provided dataset contains information on 426K cars to ensure speed of processing. Your goal is to understand what factors make a car more or less expensive. As a result of your analysis, you should provide clear recommendations to your client -- a used car dealership -- as to what consumers value in a used car.
### Deliverables
The car dealer could be interest in predicting the price of a car based on its attributes. More precise, we try to answer to the following business questions:

+ Is the price of a car related to the number of Cylinders?
+ Is the price of a car related to the Make, Model, year?
+ Is the price of a car related to the current milage/odometer?
+ Is the price of a car related to the MPG? Can the price of a car be predicted based in its attribute with reasonable accuracy?


### Business Understanding
From a business perspective, we are tasked with identifying key drivers for used car prices. In the CRISP-DM overview,
we are asked to convert this business framing to a data problem definition. Using a few sentences, reframe the task as a
data task with the appropriate technical vocabulary.

### Steps 
1. Data understanding/Load the data and familaize with it.
	+ An inventory of the dataset
	+ Identify which features are continuous and numerical versus which are discrete and categorical.
	+ Explore the unique range of categorical data.
	+ See the available columns and their data-types.
	+ Some standard details like the min, max, std-dev of the numerical variables and possible values in the categorical variables
	+ What percentage of data has null values. Start thinking about how to deal with them. Is there a logical way of filling the null values?
	+ Are there unreasonable values in the numerical variables. 	
	+ Check the histograms and distributions to understand if scaling is needed
2. Data Preparation
	+ Drop features that are not required/imiportant to the the price of a vehicle.
	+ Initaial Check and removal duplicates
	+ Window the appropriate ranges of the features and targets
	+ Impute missing values for a numerical feature using the average of the nearest three values (KNNimputer).
	+ Impute missing values for a categorical feature using the most frequest category than dropping the entire data (SimpleImputer).
	+ Drop the "Model" category as it got 29650 different models of car the will complicate our model.
	+ Up on exploration of the dataset using graphs follow Windowing of the dataset based on Price, year and Mileage/Odometer.
	+ Outlier detection and removal.
	+ Final check and removal of duplicates.
	+ Logarithmic and exponential transformations of the target (price) to achieve normal distributions.
	+ Identify the features and target for regression.
	+ Split dataset for training and teseting.
3. Modeling
	+ Column transformer for encode the categorical with oneHotEncodig and the 'Condition' column with ordinalEncoder.
	+ firs create a basline modeling with LinearRegression.
	+ Set up a pipeline workflow to handle the transformations and linear regressions
	+ Run LinearRegression model compare MAE and plot.
	+ Model and compare Ridge and LASSO linear regression models
	+ Set up a grid search to determine the best regularization hyperparameter alpha. The regularization approach allows us to include many features without overfitting.
	+ Examination of the observed and predicted target "independent" variables
	+ Cross validation to check for overfitting
4. Evaluation
	+ Analysis of Resulting Coefficients
	+ Ranking of Coefficients

5. Deployment
	+ Direct application: Comparison of the regression model to kbb.com price estimate
	+ Observations/findings
	+ Future Plan


## Observations

After the data is cleaned up and processed these are some of the observations drawn.

1. We have about 51% accuracy of the three models tried (LinearRegression, Ridge and LASSO)

2. Both regression models (Ridge and LASSO) resulted in similar ordering of coefficients and resulting weights.From the categorical coefficients we observe that manufatures type does singnificantly influence decision making in the used car buying and selling bussiness.

3. Between Year and Price there is a positive correlation, meaning that the higher is the Year (more recent), the higher is the Price (more recent cars cost more). Between Price and Mileage there is a negative correlation, meaning that higher is the mileage, lower is the Price (cars with high mileage cost less).

4. We also noticed that vehicles with 10 and 8 Cylinder size, diesel, pickup and truck have a higher ranking but cars with Cyliinder size 3 are ranked low along with Harley Davidson vehicles/bikes.

5. From the categorical coefficients we see that trucks, offroad, pickup vehicles are weighted higher. Electric vehicles in general are ranked low.

6. The car features Manufacturer, year, cylinders, and Mileage were the most important one.

7. We identify some variability in several coefficients that indicate that they are not well resolved. These include 'other' categories (e.g., fuel_other, type_other, cylinder_other) that may not be well represented in the dataset. Also, less represented features like 3-cylinders, off-road, bus, fuel_electric may not be well represented in the dataset.

8. Both models show that Tesla and Porsche have high positive weight and Mercury and Fiat have strong negative weight. Among the numerical features  the year has a high positive weight with log10-price and Mileage has a strong negative weight as shown in the correlation analysis. 

9. We tried to demonstrate that for two vehicles I own (2019 Kia and 2007 Toyota Camr) but  the model predicts the value of the vehicle within the range of the Kelly Blue Book value (kbb.com). This demonstrates the usefulness of the model.


---

For more, please open up the Jupyter notebook with plots and markdowns in this.



## Thank you

 