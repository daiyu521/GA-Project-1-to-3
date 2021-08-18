# Project 2 : Ames Housing Data and Kaggle Challenge

## Executive Summary

[Ames is a city in Iowa, United States, located approximately 48 km north of Des Moines in central Iowa. It is best known as the home of Iowa State University (ISU), with leading agriculture, design, engineering, and veterinary medicine colleges. In 2019, Ames had a population of 66,258. Iowa State University was home to 33,391 students as of fall 2019, which make up approximately one half of the city's population.](https://en.wikipedia.org/wiki/Ames,_Iowa) As an employee of a new start-up housing agency company located in Ames, who acts as a middleman between housing buyers and sellers. I was tasked to analyze the data to help the company earn a healthy commission by assisting people in finding accommodation or office space that meets their needs at a price that is agreeable to the seller. As the housing agent brings buyers and sellers together, the right approach of Negotiation on the buyer or seller behalf and disclosing any conflicts between buyers and sellers is essential for the business growth for short-term goals and the company reputation for the long term goal.

Housing agent uses their local housing market knowledge to bridge the information gap between potential buyers and sellers and help them reach the final agreeable price. Top-earning housing agents have one thing in common: They know their local housing market very well. As we are new to this game, fully understand market conditions will help us advise our clients better, position clients' housing correctly against the competitions, and keep in check if clients' expectations are reasonable. In this project, we will use the [Ames housing data available on Kaggle](https://www.kaggle.com/c/house-prices-advanced-regression-techniques) to address the above by:

- 1) Identifying the essential influence factors for the housing price
- 2) Developing a model to estimate the cost based on features.


Further, we will evaluate and optimize our model using a few validation/optimization techniques, e.g., k-fold cross-validation, train/test split validation, and regression metrics comparison. We will access our model's accuracy, precision, and ability to generalize the new data to provide our business representatives and their clients possible market recommendations. 

#### Contents:

-  Data Cleaning and EDA
-  Data Preprocessing and Feature Engineering
-  Model fitting and Evaluation 
-  Model Tuning and Evaluation
-  Conclusions and Recommendations               

#### Data Dictiornary
We are using [Ames housing data available on Kaggle](https://www.kaggle.com/c/house-prices-advanced-regression-techniques), train set data contains the same features with the test set data except test set exclude the SalePrice feature. You may find the detailed [data description](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt) below:

|Features                    | Type    |Description
|:---------------------------|:--------|:----------------------------------------------------------------------------------------
| MS SubClass                | object  |Identifies the type of dwelling involved in the sale
| MS Zoning                  | object  |Identifies the general zoning classification of the sale
| Lot Frontage               | float64 |Linear feet of street connected to property
| Lot Area                   | int64   |Lot Area (Continuous): Lot size in square feet
| Street                     | object  |Type of road access to property
| Alley                      | object  |Type of alley access to property
| Lot Shape                  | object  |General shape of property
| Land Contour               | object  |Flatness of the property
| Utilities                  | object  |Type of utilities available
| Lot Config                 | object  |Lot configuration
| Land Slope                 | object  |Slope of property
| Neighborhood               | object  |Physical locations within Ames city limits (map available)
| Condition 1                | object  |Proximity to various conditions
| Condition 2                | object  |Proximity to various conditions
| Bldg Type                  | object  |Type of dwelling
| House Style                | object  |Style of dwelling
| Overall Qual               | int64   |Rates the overall material and finish of the house
| Overall Cond               | int64   |Rates the overall condition of the house
| Year Built                 | int64   |Original construction date
| Year Remod/Add             | int64   |Remodel date (same as construction date if no remodeling or additions)
| Roof Style                 | object  |Type of roof
| Roof Matl                  | object  |Roof material
| Exterior 1st               | object  |Exterior covering on house
| Exterior 2nd               | object  |Exterior covering on house
| Mas Vnr Type               | object  |Masonry veneer type
| Mas Vnr Area               | float64 |Masonry veneer area in square feet
| Exter Qual                 | object  |Evaluates the quality of the material on the exterior
| Exter Cond                 | object  |Evaluates the present condition of the material on the exterio
| Foundation                 | object  |Type of foundation
| Bsmt Qual                  | object  |Evaluates the height of the basement
| Bsmt Cond                  | object  |Evaluates the general condition of the basement
| Bsmt Exposure              | object  |Refers to walkout or garden level walls
| BsmtFin Type 1             | object  |Rating of basement finished area
| BsmtFin SF 1               | float64 |Type 1 finished square feet
| BsmtFin Type 2             | object  |Rating of basement finished area (if multiple types)
| BsmtFin SF 2               | float64 |Type 2 finished square feet
| Bsmt Unf SF                | float64 |Unfinished square feet of basement area
| Total Bsmt SF              | float64 |Total square feet of basement area
| Heating                    | object  |Type of heating
| Heating QC                 | object  |Heating quality and condition
| Central Air                | int64   |Central air conditioning
| Electrical                 | object  |Electrical system
| 1st Flr SF                 | int64   |First Floor square feet
| 2nd Flr SF                 | int64   |Second floor square feet
| Low Qual Fin SF            | int64   |Low quality finished square feet (all floors)
| Gr Liv Area                | int64   |Above grade (ground) living area square feet
| Bsmt Full Bath             | float64 |Basement full bathrooms
| Bsmt Half Bath             | float64 |Basement half bathrooms
| Full Bath                  | int64   |Full bathrooms above grade
| Half Bath                  | int64   |Half baths above grade
| Bedroom AbvGr              | int64   |Bedrooms above grade (does NOT include basement bedrooms)
| Kitchen AbvGr              | int64   |Kitchens above grade
| Kitchen Qual               | object  |Kitchen quality
| TotRms AbvGrd              | int64   |Total rooms above grade (does not include bathrooms)
| Functional                 | object  |Home functionality (Assume typical unless deductions are warranted)
| Fireplaces                 | int64   |Number of fireplaces
| Fireplace Qu               | object  |Fireplace quality
| Garage Type                | object  |Garage location
| Garage Finish              | object  |Interior finish of the garage
| Garage Cars                | float64 |Size of garage in car capacity
| Garage Area                | float64 |Size of garage in square feet
| Garage Qual                | object  |Garage quality
| Garage Cond                | object  |Garage condition
| Paved Drive                | object  |Paved driveway
| Wood Deck SF               | int64   |Wood deck area in square feet
| Open Porch SF              | int64   |Open porch area in square feet
| Enclosed Porch             | int64   |Enclosed porch area in square feet
| 3Ssn Porch                 | int64   |Three season porch area in square feet
| Screen Porch               | int64   |Screen porch area in square feet
| Pool Area                  | int64   |Pool area in square feet
| Pool QC                    | object  |Pool quality
| Fence                      | object  |Fence quality
| Misc Feature               | object  |Miscellaneous feature not covered in other categories
| Misc Val                   | int64   |$Value of miscellaneous feature
| Mo Sold                    | object  |Month Sold (MM)
| Yr Sold                    | object  |Year Sold (YYYY)
| Sale Type                  | object  |Type of sale
| SalePrice                  | int64   |Sale price
| Lot Area * Frontage        | float64 |combined feature
| Year Built* Year Remod/Add | int64   |combined feature

#### Conclusion and Recommedations

With 81 explanatory variables describing every aspect of residential homes in Ames, Iowa, the data sets have quite many missing and outliers in the datasets. I spent a lot of time understanding all the features and replacing the missing values with another a suitable value instead. For the outliers, I decided to keep them as the data number is not very large <2500. The removal of outliers will significantly affect the model, and none of the outliers are identified as causing by entry/measuring errors.
 
Further, I also exploratory the relationships of every variable to the target "SalePrice" several variables were identified to have a massive impact on SalePrice like Total Bsmt Area, Year built, Overall Qual. I also could figure out how a single variable will affect the SalePrice like house with Excellent Kitchen Quality tend to have better SalePrice and home with Neighborhood in Northridge, Stone Brook, and Northridge Heights tend to have high sales price.

However, when bringing all the variables together, for example, what is the possible sale price for a house with a Neighborhood in Northridge but low kitchen Quality?, there is no clue for such questions. Thus, I developed a model to predict the price of dealing with such a situation.

During the Feature engineering, there are two methods I used to select the features for modeling. The first method is to manually choose the features by evaluating their correlation coefficients with SalesPrice and manually combine/drop the variables contain multi-collinear.The second method I use lasso model as a feature-pre-screening tool. There are three models: lineargression, Ridge, and lasso are used for each method. In method 1, lasso gave the best performance among the three models. In method 2, Ridge gave the best performance among the three models

|               |Method 1 lasso |Method2 ridge  |
|--------       |----------     |---------------|
| Train R2 score|  0.80         |  0.88         |  
| Test R2 score |  0.86         |  0.90         |
| MSE           |843694734      |639873210      | 

The method one lasso R2 score for Train and Test data set is 0.80 and 0.86 scores. Method 2 ridge R2 score for train and test data set are 0.88 and 0.9, respectively. Their results do not seem bad. However, Method one lasso model appears the overfitting as the higher variance between train and test set R2 score. The MSE for method one is also higher than method two. Method2 is much better than method1 in R2 score and MSE. let us see the prediction graph for method2 in below

<img src="pictures\method2_prediction.png" width="40%">

Let us compare it with method one graph. Obviously, Method Two prediction results are more closer to actual value.

<img src="pictures\method1_prediction.png" width="40%">

And we also look at the distribution of residuals. The residual plot in method 2 is about the normal distribution.

<img src="pictures\method2_residual.png" width="40%">

However, for method one, the residual plot is positively skewed, indicating high variance existing in the model.

<img src="pictures\method1_residual.png" width="40%">

The result shows method two Ridge model has better accuracy, better ability to generalize new data, and lower variance than the Method 1 lasso model. Also, in the Kaggle competition submission, the predicted value generated by method one scored around 40000000000, which is an awful score, but method two achieved around 29000.

#####                                                                                  
                                           figure 1. Kaggle Competition Scores 

<img src="pictures\submission_score.png" width="50%">

To better understand market conditions and improve our services, I believe the method two ridge model is good enough to make predictions for the AMES house price by providing the same format of housing features. It gives our business representative a rough price guideline when dealing with the clients for advising and negotiation. Its coefficient plot shows important business insights regarding the essential factors that could influence the housing price.

#####                                                                                  
                                             figure 2. Coefficients Bar Plot 

<img src="pictures\coef.png" width="100%">

The house with larger above grade (ground) living area, Lot area, and lot frontage tend to have better sales price; people would like to pay higher costs for the new houses or houses with excellent quality and condition. A so-so Kitchen Quality, Cinder Block foundation type and Garage location attach to home will harm sales price. Homes located in Northbridge and Crawford are more experience than located in College Creek and Northwest Ames. 

Finally, we would like to collect more extensive and balanced housing data from different Neighborhoods to zoom into particular areas and analyze details to advise more efficient and accurate business insights.


```python

```
