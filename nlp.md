# 自然語言處理






---
## 中文語言處理平台
- [語言雲](http://www.ltp-cloud.com)
- [玻森](http://bosonnlp.com/)
 


---
## R 自然語言處理套件

<https://cran.r-project.org/web/views/NaturalLanguageProcessing.html>


- `openNLP`：Apache OpenNLP Tools Interface.
- `NLP`: Basic functions for Natural Language Processing.
- `coreNLP`：史丹佛大學自然語言處理工具集
- `KoNLP` 韓語自然語言處理
- `tmcn` 適應中文的 `tm` 改良，方便編碼轉換。
- `jiebaR`，`Rwordseg`中文斷詞

以下用 <a href=cran.r-project.org/web/packages/coreNLP>`coreNLP`</a> 為例

```{r}
devtools::install_github("statsmaths/coreNLP")
download.file("http://nlp.stanford.edu/software/stanford-corenlp-full-2015-01-29.zip")
unzip("stanford-corenlp-full-2015-01-29.zip")
```

```{r}
library(coreNLP)
initCoreNLP("stanford-corenlp-full-2015-01-29")
catInHat = c("the sun did not shine.", "it was too wet to play.","so we sat in the house all that cold, cold, wet day.")
output = annotateString(catInHat)
getToken(output)
getDependency(output)
getSentiment(output)
```
