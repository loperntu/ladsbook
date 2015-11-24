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








