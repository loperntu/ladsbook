# 機器學習

* 監督式學習：分類\(Classification\)、迴歸分析\(Regression\)
* 非監督式學習：分群\(Clustering\)
* 訓練、測試與評估概念

### 機器學習基本想法

* 從過往資料的特徵來對未知資料做預測判斷。
* 例子：書籍或電影推薦、匯率預測、從臉書資料分類朋友人格

### 爭論

* 機器學習通常涉及預測模型 \(prediction models\)，而訓練 prediction models 通常需要有（人工）標記的資料 \(labeled data\)，換句話說，機器可以學習的**正確答案**。
* 但是有人工標記的資料（據說）耗時費事，重點是花錢，所以儘量不依賴人工標記的資料的作法漸漸受到歡迎。近年來`深度學習`神經網路演算法因為它在許多領域的成功，更是紅透半邊天。語言學與知識工程則打入冷宮。

```text
爭論的底層其實涉及更深一層的哲學問題：知識和知識的表徵是什麼？
讓機器*自己學習*很酷，但是不知道機器學習的機制來自什麼人類認知機制
不是很危險的一件事？
```

另一種反擊（個人見解）

* 花大錢的迷思：想想 `wikipedia` 是怎麼完成的？人類自己的無私熱情可以解決人類的處境。甚至 `Game with a purpose` 利用遊戲讓人不知不覺「標記」知識與常識也是個做法。
* 大數據的假說 \(let big data speak for themselves\)：巨量資料中的雜訊可以在計算過程中被處理。在文本處理是否如此需要證明！
* **Active Learning** attempts to reduce the number of labeled data needed for training the model. 把 label 當成是成本問題。
  1. Classify the document using the current decision model. Let $$C$$ be the assigned category.
  2. If $$Prob(C) <$$ threshold, request a label; otherwise, ignore the document.

> Experimenting with text categorization and with some numerical data-mining applications, researchers have found that active learning can often drastically reduce their overall sample size while achieving results comparable to training on the full set of labeled documents.\(Weiss et al. 2005\)

### 監督式學習 \(Supervised learning\)

* 資料前處理（準備好訓練與測試語料）
* 訓練機器學習模式
* 測試與效能評估
* 分析與參數調整，重新建模

```text
# 載入訓練與測試語料 
x_train <- input_variables_values_training_datasets 
y_train <- target_variables_values_training_datasets 
x_test <- input_variables_values_test_datasets
x <- cbind(x_train,y_train)
# Train the model using the training sets and evaluate
```

### 分類 Classification

* 給訂標記好的資料，選用分類演算法訓練分類器，用來預測新資料的所屬的類別。

### 分群

* 組內差異小、組間差異大的預設

### 迴歸分析

#### Random Forest

```text
# Import required Library
library(randomForest)
# Fitting model
fit <- randomForest(Species ~ ., x, ntree = 500) 
summary(fit)
# Predict Output
predicted <- predict(fit, x_test)
```

#### Gradient Boosting and AdaBoost

```text
library(caret)
# Fitting model
fitControl <- trainControl(method = "repeatedcv", number = 4, repeats = 4)
fit <- train(y ~ ., data = x, method = "gbm", trControl = fitControl, verbose = FALSE) 
predicted <- predict(fit, x_test, type= "prob")[,2]
```

### 非監督式學習 \(Supervised learning\)

* 降維技術 \(PCA, ...\)

```text
library(stats)
pca <- princomp(train, cor = TRUE) 
train_reduced <- predict(pca, train) 
test_reduced <- predict(pca, test)
```

#### Hierarchical Clustering

### Reinforcement learning

#### Markov Decision Process

## Evaluation of Performance

評量機器學習模型的表現

深入鑽研

[Andrew Ng, Machine Learning](https://www.coursera.org/learn/machine-learning)

[Johns Hopkins University, Practical Machine Learning](https://www.coursera.org/learn/practical-machine-learning)

[林軒田，機器學習基石](https://www.youtube.com/user/hsuantien/playlists)

[林軒田，機器學習技法](https://www.youtube.com/playlist?list=PLXVfgk9fNX2IQOYPmqjqWsNUFl2kpk1U2)

