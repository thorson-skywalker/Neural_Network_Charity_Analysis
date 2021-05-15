# Neural Network Charity Analysis

## Purpose

The purpose of this project was to use neural netowrks and deep learning models to analyze the success of Charity donations given to various organizations so that we can further use the model to predict if future donations will be successful.

## Results

# Initial Analysis



# Optimizations

- First Optimization Attempt

![](Resources\images\optimization1.PNG)

The first optimization involved removing the 'ORGANIZATION' and 'SPECIAL_CONSIDERATIONS' columns to try and pare down what could be uneccessary data. unfortunately this optimization was unseccessful as the accuracy result was approximately the same as the initial analysis at 72.6%

- Second Optimization Attempt

![](Resources\images\optimization2.PNG)

For the second optimization attempt the 'ORGANIZATION' and 'SPECIAL_CONSIDERATIONS' columns were returned and the 'AFFILIATIONS' column was removed, as the affiliation of the organization might not have an effect on the result. A third hidden layer was also added with 10 nodes, with the presumption that passing through more nodes might assist the model's accuracy. However, this was not the case as the resulting accuracy was reduced to aproximately 65.4%.

- Third Optimization Attempt

![](Resources\images\optimization3.PNG)

With the reduced accuracy in the second attempt, overfitting became a concern for the model. To counter this, in the third opitmization attempt, the third hidden layer was removed, and the number of nodes in layers 1 & 2 were reduced to 60 and 20 respectively. Also, the values were increased for the "other" application_type bin to 750. This would add three application_types to the rare_type bin under presumption it would make the data more uniform and thus the model more accurate. This was not the case. Instead the accuracy of the model was reduced to 65.6%.

- Fourth Optimization Attempt

![](Resources\images\optimization4.PNG)

The results of optimization attempts 1 & 2 suggested that the 'AFFILIATION' column was in actuality very important to the model. For this attempt all changes from the previous attempt were kept, but the 'AFFILIATION' column was returned to the model. This was a good assumption as it did lead to an increase in the accuracy of the model to 73.1%.