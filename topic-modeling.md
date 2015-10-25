# Topic Modeling



* Topic modeling 指的是一組從文集中抽取隱藏「主題」thematic structures 的技術方法。

* 最早的模型是 **pLSI** (probabilistic latent semantic indexing) ，後來發展的 **LDA** (Latent Dirichlet allocation) (LDA,潜在狄利克雷分配模型) 模型及其延伸變成了最常用的模型。LDA topic model 涉及比較深一點的數學，包括 Dirichlet distribution, 多項分佈、EM 算法、Gibbs sampling 等等。

* Topic modeling treats each document as a **bag of words** in which word order is disregarded. 把整個文本當成是詞的集合，至於語法或任何詞序都可以忽略掉。

## LDA

LDA 是一个三层的贝叶斯概率模型。不论 PLSI 还是 LDA,都遵循一个通式:


$$ 
P(w|d) = \Sigma p(w|z) * p(z|d) 
$$





----
## Topic model with R


- `mallet`:
- `topicmodels`: Topic modeling interface to the C code developed by by David M. Blei for Topic Modeling (Latent Dirichlet Allocation (LDA), and Correlated Topics Models (CTM)).
- `lda`
- `LDAvis` Interactive visualization of topic models.




