

Iris Species Prediction
========================================================
author: Treehouse
date: Jul 2015
transition: rotate
type: section

THE IRIS DATASET
========================================================
Introduced by statistician Ronald Fisher

3 species of Iris:
  - setosa
  - virginica
  - versicolor
  
4 measurements:
  - Sepal: lenght and width (in cm.)
  - Petal: length and width (in cm.)
  

Prediction used 2 different Models
========================================================
This App allows users to interactively choose each measure:

  * Sepal: lenght and width (in cm.)
  * Petal: length and width (in cm.)

Two models are used in the app:

1. K-Nearest Neighbor

2. Decision Tree

K-Nearest Neighbor
========================================================




```r
prediction <- knn(train_input, test_input, train_output, k=5)
table(prediction, iristest$Species)
```

```
            
prediction   setosa versicolor virginica
  setosa         10          0         0
  versicolor      0         10         1
  virginica       0          0         9
```

Decision Tree Model
========================================================


```r
set.seed(33488)
treeModel <- rpart(Species ~ ., data=iristrain, method="class")
prediction <- predict(treeModel, newdata=iristest, type='class')
table(prediction, iristest$Species)
```

```
            
prediction   setosa versicolor virginica
  setosa         10          0         0
  versicolor      0         10         3
  virginica       0          0         7
```


Based on the two results - KNN model has slightly better result.

