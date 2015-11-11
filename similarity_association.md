# 文本相似與關聯計算
Similarity and Association

## 文本相似度
- The concept of **similarity** is quite elusive.
- 先定義好在妳的應用中「相似」是什麼意思，再來想數學模式。

#### 文本相似度的幾何詮釋
- 把文本相似度的量度表徵為幾何空間的距離 (distance measure)，是常用的作法。
- `Cosine similarity` 被認為比 `Euclidean` 還有效率。[^1] 
以下計算 `cosine similarity` 的例子來自 [^2]
    

![](cosine.jpg)

假設有三份文件，分別各只有一句話。

    Text 1: statistics skills and programming skills are equally important for analytics
    Text 2: statistics skills and domain knowledge are important for analytics
    Text 3: I like reading books and travelling

文詞矩陣`dtm` 就會長成這樣
![](dtm.jpg)

三個文本的簡易向量表達就會是 
    
    T1 = (1,2,1,1,0,1,1,1,1,1,0,0,0,0,0,0)
    T2 = (1,1,1,0,1,1,0,1,1,1,1,0,0,0,0,0)
    T3 = (0,0,1,0,0,0,0,0,0,0,0,1,1,1,1,1)

將文本表徵成這樣，就可以用 `cosine similarity`來算它們之間的「相似度」。

$$sim(T1,T2) = (T1 * T2) / (\sqrt(\sigma(T1^2)) * sqrt(sum(T2^2))) = 77%
$$


$$
Degree of Similarity (T1 & T3) = (T1 %*% T3) / (sqrt(sum(T1^2)) * sqrt(sum(T3^2))) = 12%
$$









----

## Multidimensional scaling

    * Multidimensional scaling takes a table of similarities among words and turns it into a visual display like a map showing distances among words.And you can use a diagram called **word cloud** to display the results.

    * Extending word clouds with covers: 
Drawing boundaries around groups of words is one way to get some of this information. These boundaries are called **covers**. Covers surround the places in the chart where similar words congregate together.(Stuhl, 2015)

![Word cloud with convex hull covers](wordcloud.jpg) 



Word cloud with Kernel density covers

![Word cloud with Kernel density covers](wordcloud2.jpg)



## 字詞的熱力圖

Heat maps of words

## 文本網路

Graph layout of words

---
[^1] [Space and Cosine Similarity measures for Text Document Clustering](http://www.ijert.org/view-pdf/2373/space-and-cosine-similarity-measures-for-text-document-clustering)

[^2] https://manoharswamynathan.wordpress.com/category/text-mining/
