# Feature Engineering 
The goal of feature engineering is to make your data better suited to solve the problem.

The advantages of feature engineering is that it could: 
- improve the model's predictive performance 
- less computational and data needs
- improve the interpretibility of the results

## Mututal Information 

### Background 
Feature Utility Metric is used a broad term to indicate a preliminary tactic to narrow down the features that are actually helpful to your model. A type of feature utility metric is "mutual information". It measures the associate between the feature and the target. More specifically it is the knowledge of one quantity that reduces the uncertainity of another quantity. For example, if we're trying to predict the home price, the exterior quality of home provides us with more insight into guessing the price. 

### univariate metric
Caution should be used with mututal information because it is a univariate metric. Meaning that it evaluates the predictive quality of a feature in isolation. It doesn't tell you have useful it could be it combination with other features. 

### interpreting mututal information metric
0 = no associate between the feature the target 
2+ = very uncommon (Mutual information is a logarithmic quantity, so it increases very slowly.)
