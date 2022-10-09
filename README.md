# Machine-Learning-Capstone-Project
Predict Vehicles Price with Machine Learnings

### INTRODUCTION
We will make predictions by training the dataset of car features and car sales prices. The target and the features are given both in this dataset and the target is continous variable. This case will be supervised machine learning tasks. 



### Steps to follow ;
* 1. Acquire
> * Explore Problem 
> * Identify Data 
> * Evulation
* 2. Understanding and Exploring Data 
> * Import Statement 
> * Load Data
> * Combine Data 
> * Cleaning Data
> * Data Visulation
* 3. Descriptive Statistics
* 4. Prepare Data for Models
> * Prepare Features
> * Split Data into Train and Test
* 5. Model Selection
> * Random Forest Regressor
> * Ridge Regressor
> * Lasso Regressor
> * Linear Regression

* 6. Conclusion

![new](https://github.com/skrbyrm/Machine-Learning-Capstone-Project/blob/Capstone/img/Capture.PNG)

First, the fragmented data in the folder is called and merged. By applying **data cleaning steps**, outliers, null values and duplicate data were cleaned. Some **outliers** row are filled with **mean** values to avoid data loss.

The **statistical relationship** between the **features** and the **target**  was examined and it was deemed appropriate to use all of the variables.

Features of String data type are converted as **dummy** and **categorical**. Thus, two independent datasets were created.

**Fandom Forest**, **Ridge**, **Lasso** and **Linear Regression** libraries were used during the building of the models.

**Random Forest Regressor** was run with default parameters in the first model. A good result was obtained, but for the possibility of overfit and a better RMSLE value, the **parameter_grid** is defined where different parameters are include. Randomized parameters were applied using the **randomized_searchCV** function and the best parameters were selected. Considering the size of the data, **n_iter = 10** and **cv=5** were chosen.
The same function was applied separately in dummies and data sets with categorical features. Thus, the parameters that give the lowest value for RMSLE are registered as **best_params**.
In each trial, the model run time lasted for a minimum of 12 minutes.

**Linear Regression** was run with the **cross_val_score** function by selecting **cv=10**. Two models were created by testing Normal Price and Logarithmic Price. The logarithmic Price Model gave a better result than the Normal one. The error calculation function was recalculated by applying the inverse logarithm and the scores were printed clearly. These models gave very **fast results**. However, results were not as good as Random Forest Regressor.

**Ridge and Lasso** have been tested because they are resistant to overfitting. It was observed that they gave better results when the number of features increased. However, worse results were obtained than Random Forest Regressor and Linear Regression.

**As a result**; With the **sort_values(by="Test RMSLE", ascending=True))** command, the **RMSLE** score is sorted in ascending order and the above table is obtained. According to the obtained scores, it was seen that the best madel for this case was **Random Forest Regressor**.


