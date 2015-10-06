# 機器學習基本概念

* 監督式學習
* 非監督式學習
* 訓練、測試與評估







### 監督式學習 (Supervised learning)

資料前處理

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
# grow tree
fit <- rpart(y_train ~ ., data = x, method="class")
summary(fit)
# Predict Output
predicted <- predict(fit,x_test)

```



#### kNN






#### 羅吉斯迴歸 logistic regression



#### Random Forest




---
### 非監督式學習 (Supervised learning)


#### k-means


#### Hierarchical Clustering





---
### Reinforcement learning

#### Markov Decision Process










