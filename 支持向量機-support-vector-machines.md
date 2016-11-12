### 支持向量機 Support Vector Machines \(SVM\)

* 找到一個超平面，使得兩個類別的集合儘量地分開，換句話說，讓邊界達到最大。

```
# Import required library
library(e1071)

# Fitting model
fit <- svm(y_train ~ ., data = x)
summary(fit)

# Predict Output
predicted <- predict(fit, x_test)

```

