# 主題模型 Topic Modeling



* Topic modeling 指的是一組從文集中抽取隱藏「主題」thematic structures 的技術方法。

* 最早的模型是 **pLSI** (probabilistic latent semantic indexing) ，後來發展的 **LDA** (Latent Dirichlet allocation) (LDA,潜在狄利克雷分配模型) 模型及其延伸變成了最常用的模型。LDA topic model 涉及比較深一點的數學，包括 Dirichlet distribution, 多項分佈、EM 算法、Gibbs sampling 等等。

* Topic modeling treats each document as a **bag of words** in which word order is disregarded. 把整個文本當成是詞的集合，至於語法或任何詞序都可以忽略掉。

## LDA

LDA 是一個貝氏機率模式，不管 PLSI 還是 LDA 都遵循以下通式:


$$ 
P(w|d) = \Sigma p(w|z) * p(z|d) 
$$





----
## Topic model with R


- `mallet`:
- `topicmodels`: Topic modeling interface to the C code developed by by David M. Blei for Topic Modeling (Latent Dirichlet Allocation (LDA), and Correlated Topics Models (CTM)).
- `lda`
- `LDAvis` Interactive visualization of topic models.
- `RTextTools`


```r
library(RTextTools)
library(topicmodels)

# loading the data (the bundled NYTimes dataset contains headlines from front-page NYTimes articles)
# 隨機挑 1000 篇
data(NYTimes)
data <- NYTimes[sample(1:3100, size=1000, replace=FALSE),]

# Create a DocumentTermMatrix
# create_matrix() 建立的 dtm 可以當topimodels 的 LDA() 的input
matrix <- create_matrix(cbind(as.vector(data$Title),
            as.vector(data$Subject)), 
            language="english", 
            removeNumbers=TRUE, 
            stemWords=TRUE, 
            weighting=weightTf)

# Perform Latent Dirichlet Allocation

## First we want to determine the number of topics in our data. 
# In the case of the NYTimes dataset, the data have already been classified as a training set for supervised learning algorithms. 
# Therefore, we can use the unique() function to determine the number of unique topic categories (k) in our data.
# Next, we use our matrix and this k value to generate the LDA model.

k <- length(unique(data$Topic.Code))
lda <- LDA(matrix, k)

# View the Results
## view the results by most likely term per topic, or most likely topic per document.

terms(lda)
topics(lda)
```



