# 支持向量機 Support Vector Machines \(SVM\)

* 在一個高維度的空間找到一個超平面，使得兩個類別的集合儘量地分開，換句話說，讓邊界達到最大。
* SVM 的演算法核心是**核方法 \(kernel methods\)。** 核方法採自水果的果核隱喻，在運作上使用所謂的「核心秘訣」，即只針對特徵空間中相關資料運算，節省了記憶體。

```
# Import required library
library(e1071)

# Fitting model
fit <- svm(y_train ~ ., data = x)
summary(fit)

# Predict Output
predicted <- predict(fit, x_test)
```



