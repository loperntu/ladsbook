# 文本清理


- 可以利用指令列。
- 可以利用 `tm` 來做。

    - 接續前一節的 character vector, 利用 `tm` 的 `Corpus()` 建立語料庫向量物件。
    ```r
    docs <- Corpus(VectorSource(files))
    ```
    - 檢視語料庫中的特定文件
    ```r
    writeLines(as.character(docs[[30]]))
    ```
    - 視需要進行各種前處理
    ```r
    # 拼音文字轉小寫
    docs <-tm_map(docs,content_transformer(tolower))
    
    # 移除可能有問題的符號
    toSpace <- content_transformer(function(x, pattern) {
        return (gsub(pattern, " ", x))
        }
    )
    docs <- tm_map(docs, toSpace, "-")
    docs <- tm_map(docs, toSpace, "’")
    docs <- tm_map(docs, toSpace, "‘")
    docs <- tm_map(docs, toSpace, "•")
    docs <- tm_map(docs, toSpace, "”")
    docs <- tm_map(docs, toSpace, "“")
```