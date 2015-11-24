# 文本聚叢 Text Clustering



- Clustering is the typical **numerical analysis** which tries to group together like observations based on commonality or closeness of the observation data points. 
- In text analysis, we are almost repeating the same operation with clusters: trying to determine the relationships between word usage across a document. **Text clustering** refers to the task of identifying the clustering structure of a corpus of text documents and assigning documents to the identified cluster(s). 
- 常用的方法：Two typical types of clustering algorithms, i.e., connectivity-based clustering (a.k.a., hierarchical clustering) and centroid-based clustering (e.g., k-means clustering).
* `k-means`clustering: reduces the sum of squares differences between relationships and group/cluster words where the distances are minimized to the thresholds specified, in this case, the number of clusters specified.




```r
> library(stats)
> mymeans <- kmeans(dtm,5)
> mymeans
```



```r
> freq <- findFreqTerms(dtm,10)
```


---
## 多向度標示法 

多向度標示法 (Multi-Dimensional Scaling, MDS) 也是一種可以用在文本分析的多變量資料分析方法。特別是希望呈現處資料內的連續結構 (向度、因素等)，而非離散結構 (分類、分割等) 的時候。





- 去摺 (unfolding) 原理可用來詮釋受試者對於物件偏好的潛在機制。將受試者和物件同時標示在同一個空間，受試者距離物件的遠近就反映他對物件的偏好程度。








