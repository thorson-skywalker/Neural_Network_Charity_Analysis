# Neural Network Charity Analysis

## Purpose

The purpose of this project was to use neural netowrks and deep learning models to analyze the success of Charity donations given to various organizations so that we can further use the model to predict if future donations will be successful.

## Results

### Initial Analysis

#### Data preprocessing
- The purpose of the project to create a model that would help us determine successful donations, the 'IS_SUCCESSFUL' column was the obvious choice for our target variable. Looking through the data, it appeared that the 'NAME' and 'EIN' columns were identification columns and would not be useful to the model, so they were removed.
- All other columns were determined to be useful to the model and kept, although there were categorical columns that would need to be analyzed for sorting into "rare type" bins. These were the 'APPLICATION_TYPE' and 'CLASSIFICATION' columns.
- After sorting those columns the data was encoded for analysis by the model. 

#### Compiling, Training, and Evaluating the Model
- Using the two-three rule of thumb to determine the number of nodes to be used in the model, 80 nodes were selected as the number of input columns was 44. While not exactly two times as many nodes, overfitting is a concern when using neural networks so the slightly reduced nodes was chosen to reduce the chance of overfitting. 
- Two layers were chosen in the hopes that it would increase the accuracy of the model.

![](Resources\images\initial_analysis.png)

- With the initial model, as seen above, 72.8% accuracy was achieved. This fell short of the target accuracy at 75%. A number of optimizations were attempted to reach this accuracy and can be seen below.

### Optimizations

#### First Optimization Attempt

![](Resources\images\optimization1.PNG)

The first optimization involved removing the 'ORGANIZATION' and 'SPECIAL_CONSIDERATIONS' columns to try and pare down what could be uneccessary data. unfortunately this optimization was unseccessful as the accuracy result was approximately the same as the initial analysis at 72.6%

#### Second Optimization Attempt

![](Resources\images\optimization2.PNG)

For the second optimization attempt the 'ORGANIZATION' and 'SPECIAL_CONSIDERATIONS' columns were returned and the 'AFFILIATIONS' column was removed, as the affiliation of the organization might not have an effect on the result. A third hidden layer was also added with 10 nodes, with the presumption that passing through more nodes might assist the model's accuracy. However, this was not the case as the resulting accuracy was reduced to aproximately 65.4%.

#### Third Optimization Attempt

![](Resources\images\optimization3.PNG)

With the reduced accuracy in the second attempt, overfitting became a concern for the model. To counter this, in the third opitmization attempt, the third hidden layer was removed, and the number of nodes in layers 1 & 2 were reduced to 60 and 20 respectively. Also, the values were increased for the "other" application_type bin to 750. This would add three application_types to the rare_type bin under presumption it would make the data more uniform and thus the model more accurate. This was not the case. Instead the accuracy of the model was reduced to 65.6%.

#### Fourth Optimization Attempt

![](Resources\images\optimization4.PNG)

The results of optimization attempts 1 & 2 suggested that the 'AFFILIATION' column was in actuality very important to the model. For this attempt all changes from the previous attempt were kept, but the 'AFFILIATION' column was returned to the model. This was a good assumption as it did lead to an increase in the accuracy of the model to 73.1%.

## Summary

While the neural network model did not achieve the target accuracy with the optimizations that were attempted in this project, further adjustments to "rare type" bins and the number of nodes to reduce overfitting would likely result in a more optimal model. However, due to the nature of the target variable, a logistic regression model would liekly be a better model to attempt for further analysis. They are faster to put together and for a binary target analysis would likely be able to achieve the same if not better accuracy.