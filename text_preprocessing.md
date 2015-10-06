# Text pre-processing



* 目的：蒐集擷取 (collecting)、清理 (cleaning) 與調整 (reshaping) 文本訊息，方便後續處理分析。
* 注意：有些作法會把表徵 (represention) 的處理放到這個部分，我們則放在文本語意的章節再談。 


> Text does not follow any regular pattern amenable to being analysed using standard statistical methods. How do we get text ready for analysis?

* A large amount of available textual data are unstructured, massive, and of tremendous variety.
* We need adjustments to these texts to make it more analyzable.
* You can use R functions/Linux command line tools for manipulating text. 
---



## 文本蒐集
來源
* 網路
* local texts
* 感測器 (透過 Speech-to-Text API)


## 基本的文本清理步驟
不一定照此順序

1. 大小寫轉換
2. 標點符號移除
3. 數字移除
3. URLs 移除
4. 表情符號 
5. 停用詞移除 (stop words removal) 
6. 詞目化 (lemmatization)、詞幹化 (stemmming) 
7. 分詞 (tokenization)
8. 詞類自動標記 (POS tagging)


## 中文文本的特殊性
* 分詞（斷詞）問題

> 字與詞的不同


<a href="http://www.youtube.com/watch?feature=player_embedded&v=YOUTUBE_VIDEO_ID_HERE
" target="_blank"><img src="http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg"
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>


> `jiebaR`, `Rwordseg`


---
進階：XML 文件處理參見 附錄




