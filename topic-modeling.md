# Topic Modeling



* Topic modeling 指的是一組從文集中抽取隱藏「主題」thematic structures 的技術方法。

* 最早的模型是 **pLSI** (probabilistic latent semantic indexing) ，後來發展的 **LDA** (Latent Dirichlet allocation) (LDA,潜在狄利克雷分配模型) 模型及其延伸變成了最常用的模型。LDA topic model 涉及比較深一點的數學， 包括 Dirichlet distribution, 多項分佈、EM 算法、Gibbs sampling 等等。

* 

## LDA

LDA 是一个三层的贝叶斯概率模型,且有一个假设:bag of word。意思就是认为文档就是一个词的集合,忽略任何语法或者出现顺序关系。不论 PLSI 还是 LDA,都遵循一个通式:


$$ 
P(w|d) = \Sigma p(w|z) * p(z|d) 
$$



简单的说,即为两种分布:一种是 topic-word 分布,即 p(w|z),一种是 doc-topic 分布,即 p(z|d),而这两者构成了 word-topic-doc 的关系。



doc topic 这一级,PLSA 把这一级的所有变量都看作模型的参数,即有多少文档那么就有 多少模型的参数;而 LDA 引入了一个超参数,对 doc topic 这一个层级进行 model。这样无论 文档有多少,那么最外层模型显露出来的[对于 doc topic]就只有一个超参数。

最基本的 PLSA 和 LDA 在刻画 doc topic 和 topic word 都利用了一个模型,就是 multi- nomial model。为了计算的方便及先验的有意义,共轭先验是首选。multinomial distribution 的共轭分布是 Dirichlet distribution,很 nice 的一个分布。这也是 Latent Dirichlet Allocation 中 Dirichlet 的由来。




## Topic model with R
`mallet`, `topicmodels`, `lda`




