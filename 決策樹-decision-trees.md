# 決策樹 Decision Tree

* 以樹狀來表達資料流 \(tree-based\) 的一種監督式機器學習\(supervised machine learning\)演算法。
* 使用**分治法 \(divide and conquer\)：**讓資料從樹根 \(root\) 開始，根據特定條件選擇最佳的分支屬性，而在每個節點形成分支，直到所有資料都被指定到葉節點 \(leaf node\) 為止。



#### 考量 

* 訓練資料愈多愈好。
* 可選擇的變數愈多愈好。
* 好的決策樹應該精簡，只預測最少數量的問題。



製作決策樹有不同考量，依照以下作法不同，而有不同的演算法，如 `C5, CART,CHAID `等。

* 分支判準 splitting criteria

* 停止條件

* 修剪時機



```
# Import required library
library('rpart')

# Fitting model (growing tree)
fit <- rpart(y_train ~ ., data = x, method="class")
summary(fit)

# Predict Output
predicted <- predict(fit, x_test)
```







