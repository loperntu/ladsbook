# 機器學習基本概念

* 監督式學習
* 非監督式學習
* 訓練、測試與評估概念







### 監督式學習 (Supervised learning)

- 資料前處理（準備好訓練與測試語料）
- 訓練機器學習模式
- 測試與效能評估
- 分析與參數調整，重新建模


```
# 載入訓練與測試語料 
x_train <- input_variables_values_training_datasets 
y_train <- target_variables_values_training_datasets 
x_test <- input_variables_values_test_datasets
x <- cbind(x_train,y_train)
# Train the model using the training sets and evaluate
```


#### 決策樹 Decesion Tree
```
# Import required library
library(rpart)
# Fitting model (growing tree)
fit <- rpart(y_train ~ ., data = x, method="class")
summary(fit)
# Predict Output
predicted <- predict(fit, x_test)
```

#### 素樸貝氏 Naive Bayes

```
# Import required library
library(e1071)
# Fitting model
fit <- naiveBayes(y_train ~ ., data = x) 
summary(fit)
# Predict Output
predicted <- predict(fit, x_test)
```


#### 支持向量機 Support Vector Machines (SVM)

```
# Import required library
library(e1071)
# Fitting model
fit <-svm(y_train ~ ., data = x) 
summary(fit)
# Predict Output
predicted <- predict(fit, x_test)
```


#### k-Nearest Neighbours (kNN)

```
# Import required library
library(knn)
# Fitting model
fit <-knn(y_train ~ ., data = x, k = 4) 
summary(fit)
# Predict Output
predicted <- predict(fit, x_test)

```



#### Random Forest

```
# Import required Library
library(randomForest)
# Fitting model
fit <- randomForest(Species ~ ., x, ntree = 500) 
summary(fit)
# Predict Output
predicted <- predict(fit, x_test)
```


#### Gradient Boosting and AdaBoost

```
library(caret)
# Fitting model
fitControl <- trainControl(method = "repeatedcv", number = 4, repeats = 4)
fit <- train(y ~ ., data = x, method = "gbm", trControl = fitControl, verbose = FALSE) 
predicted <- predict(fit, x_test, type= "prob")[,2]

```



---
### 非監督式學習 (Supervised learning)

- 降維技術 (PCA, ...)

```
library(stats)
pca <- princomp(train, cor = TRUE) 
train_reduced <- predict(pca, train) 
test_reduced <- predict(pca, test)
```



#### k-means


```
# Assumed you have X attributes for training data set 
# Import required library 
library(cluster) 
fit <- kmeans(X, 3)
```

#### Hierarchical Clustering





---
### Reinforcement learning

#### Markov Decision Process










