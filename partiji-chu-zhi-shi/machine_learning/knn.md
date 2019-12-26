# kNN

\#\#\#\# k-Nearest Neighbours \(kNN\)

\*\*k-nearest neighbors algorithm \(k-NN\)\*\* 可能是最簡單的機器學習演算法，但是在許多場合還是很好用。

* 不預設資料的分佈型態。
* 如果很難定義概念，但是知道資料何時出現時。
* 利用資料的「同類相聚」特徵，classifying unlabeled examples by assigning them the class of similar labeled examples.

\`\`\`

\# Import required library

library\(knn\)

\# Fitting model

fit &lt;-knn\(y\_train ~ ., data = x, k = 4\)

summary\(fit\)

\# Predict Output

predicted &lt;- predict\(fit, x\_test\)

\`\`\`

