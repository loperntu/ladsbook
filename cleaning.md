# 文本清理

- 可以利用 `tm` 來做。

```r
# create corpus from vector
docs <- Corpus(VectorSource(files))

 
#inspect a particular document in corpus
writeLines(as.character(docs[[30]]))

 
#start preprocessing
#Transform to lower case
docs <-tm_map(docs,content_transformer(tolower))

 
#remove potentially problematic symbols
toSpace <- content_transformer(function(x, pattern) { return (gsub(pattern, ” “, x))})
docs <- tm_map(docs, toSpace, “-“)
docs <- tm_map(docs, toSpace, “’”)
docs <- tm_map(docs, toSpace, “‘”)
docs <- tm_map(docs, toSpace, “•”)
docs <- tm_map(docs, toSpace, “””)
docs <- tm_map(docs, toSpace, ““”)


```