# 自動摘要

顧名思義，在儘可能保留文本核心語意的狀況下，將文本簡化到摘要的形式。

* Gong and Liu \(2001\) 利用分佈語意模式，從文本中找出 _k_ 個最重要的句子。 步驟如下：
  1. Decompose the text into its sentences
  2. Construct a term-by-sentence frequency matrix
  3. Perform a SVD to obtain a singular value matrix 􏰚 and a right singular vector matrix $$V^{t}$$. Each column vector of $$V^{t}$$ then represents a sentence of the original text.
  4. Select the _k'th_ right singular vector from this matrix.
  5. Select the sentence which has the largest index value with this _k'th_ right singular vector, which is then included in the summary. Given the assumption that each row vector represents a topic of the text, this is exactly the sentence that scores the highest value on this topic, compared to the other sentences.
  6. Repeat until _k_ reaches a predefined number.

```r
D <- ""
```

