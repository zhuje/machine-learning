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

## Creating Features 
This module is an introduction to common data transformations. 
1. Mathematical Transformation 
Apply a math equation to each cell. 
```
# create a ratio of two columns 
autos = pd.read_csv("../input/fe-course-data/autos.csv")
autos["stroke_ratio"] = autos.stroke / autos.bore
autos[["stroke", "bore", "stroke_ratio"]].head()
```
2. Counts 
For example, create a sum for the number of accidents in each row. 
The columns "Bump", "Crossing", "Amenity", are all types of accidents, but we want to create a column that sums the accidents for each row. 
".gt(0)" is applys the conditions " cells > 0 ? true : false " to each column, meaning if the condition is true the cell is filled in with True. Otherwise fill it with False. 
"sum(axis=1)" means sum each row. Meaning True=1, False=0.  
```
components = pd.read_csv("../input/fe-course-data/components.csv")
components = [ "Cement", "BlastFurnaceSlag", "FlyAsh", "Water",
               "Superplasticizer", "CoarseAggregate", "FineAggregate"]
concrete["Components"] = concrete[components].gt(0).sum(axis=1)
concrete[components + ["Components"]].head(10)
```

3. Building and Breaking down features (string conversion)
String conversion. We can split strings by a delimiter like .split(" ", expand=True)
```
customer[["Type", "Level"]] = (  # Create two new features
    customer["Policy"]           # from the Policy feature
    .str                         # through the string accessor
    .split(" ", expand=True)     # by splitting on " "
                                 # and expanding the result into separate columns
)

customer[["Policy", "Type", "Level"]].head(10)
```
4. Group Transformations
We wanted to create a new column called "AverageIncome" which give us the mean income by state. 
```
customer["AverageIncome"] = (
    customer.groupby("State")  # for each state
    ["Income"]                 # select the income
    .transform("mean")         # and compute its mean
)

customer[["State", "Income", "AverageIncome"]].head(10)
```