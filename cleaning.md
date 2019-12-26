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
    - 拼音文字轉小寫    
    ```r
    docs <-tm_map(docs,content_transformer(tolower))
    ```
    - 移除可能有問題的符號
    ```r
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
    - 移除標點符號 (punctuation)、數字 (digits)、空白 (white space)
    ```r
    docs <- tm_map(docs, removePunctuation)
    docs <- tm_map(docs, removeNumbers)
    docs <- tm_map(docs, stripWhitespace)
    ```
    - 停用詞 (stop words)
    ```r
    docs <- tm_map(docs, removeWords, stopwords("english"))
    ```
    可自訂詞表
    
    ```r
    myStopwords <- c("can", "it","may","might","great","kind")
    docs <- tm_map(docs, removeWords, myStopwords)
    ```
    選擇「停用詞」這是個大學問。
    
    - 語詞詞幹化 (stemmization) 
    ```r
    docs <- tm_map(docs,stemDocument)
    ```
    > 注意養成資料分析好習慣：隨時看看修改後的資料樣子。`writeLines(as.character(docs[[30]]))`
    
    - 語詞詞形化 (lemmatisation) 
    
- 表情符號 (Emoticon)

    表情符號在社群媒體的意義重大，是當代語言使用的一大特點。可參考 [^1]
    
    
    
---
[^1] [Emoticons decoder for social media sentiment analysis in R](http://www.r-bloggers.com/emoticons-decoder-for-social-media-sentiment-analysis-in-r/)