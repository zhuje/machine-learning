# Categorical variables 

The goal of categorical variables is to assign numbers to text so that we can work with them in a dataframe. The categorical variables map numbers to categories. 

For example, if there is a survey to car owners on what brand they drive, categories could include Honda, Toyota, and Ford. 
We need to convert these categoriges include values. 

There are three approaches: 
1. Drop Categorical Variables (typically least effective)
- drop the whole column 
- use case: only when the categorical variables are insignificant to analyzing the data 

2. Ordinal Encoding (works bests with Tree-based models)
- sequentially encode each category Honda = 1, Toyota = 2, Ford = 3 
- Usecase: Best with tree based models like DescisionTree, RandomForest, or when there are 15+ categories
![alt text](https://storage.googleapis.com/kaggle-media/learn/images/tEogUAr.png)

3. One-Hot Encoding (typically performs the best unless you have 15+ categories)
- Each category gets its own column, each row represents a response 0 = absent, 1 = present 

- Usecase: Best when you have < 15 categories. Because we're introducing alot of data and zeros to the dataframe it can lead to 1) High dimensionality; a lot of categories will take more computational and memory resources 2) spare data; a lot of zeros creates a sparse matrix which negatively impacts the model performance 3) overfitting 
![alt text](https://storage.googleapis.com/kaggle-media/learn/images/TW5m0aJ.png)

| Response          | Honda    | Toyota |
| :---------------- | :------: | ----:  |
| Honda             |   1      | 0      |
| Toyota            |   0      | 1      |
| Honda             |  1       | 0      |
| Honda             |  1       | 0      |