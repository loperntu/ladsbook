# 語言分析與資料科學 
####Linguistic Analysis and Data Science


---
## 資料科學是什麼？資料科學家會什麼

* To retrieve, transform, explore and model data as well as interprete and communicate results in a compelling way. 
* Be able to do useful real data science work with programming languages (R/Python) as well work with big data technology (Hadoop, Spark). 


---
## 語言與文本分析

* 文本四處都在，特別是網路。文本資料來源：網頁，新聞，網誌，電郵，社交媒體等等。（reviews, postings, tweets, blogs, news, articles, responses to surveys, advertisements, product descriptions, scholarly papers, emails, comments collected for insurance, retail, health care and research (to name a few)。
* 文本資料的構成：以自然語言為主，常常伴隨各種表情符號，以及其他的多媒體素材。
* 語言與文本分析的用意，就是運用語言學與文本分析的知識與技術，將文本**資料**(data)中蘊含的**訊息**(information)發掘出來，進一步轉化成**知識**(knowledge)，應用在各個領域。


## Data Science and Text Analytics


資料科學家的工作，可以視為是一個探索、預測與解讀資料意義的互動歷程。而語言分析的工作，在了解文本資料的語意與情緒表現上是重要的關鍵。本課程結合了目前統計程式設計與自然語言處理技術，以較為簡潔容易入門的設計與實際操作導引，希望可以讓毫無相關程式學習基礎的學生在本課程的帶領下，達到以下的學習目標：


1. 了解結構與非結構性資料的特性與預處理工作,特別是針對中文文本中呈現的語言特性的處理方法。
2. 了解中文的語言特性與文本解析 (text analytics) 的基本概念。
3. 選擇適當的變數與特徵並加以合理調製,對之進行描述統計與視覺探勘,針對不同的問題點與數據類型,找出適當的圖形表達與統計分析。
4. 學習簡易的自然語言處理與機器學習預測模式,並應用在自己關心的領域。


---
## 文本是什麼 Text Representation

* 文件和文本 document and text
* structured, semi-structured and unstructured data
* doc, csv, pdf, xml, html, markdown....




## 文本挖掘（文本採礦）Text Analytics/Text Mining

<!-- A common use of data mining is to detect patterns or rules in data.
-->

* 文本挖掘可以被定義成`以自動化或半自動化文本處理方法，挖掘文本中的知識的歷程`。

* You do not need to have **big data** to do text analytics. The methods work with large, medium and small datasets.

* 通常的應用涉及了文本分類與叢聚、模式與趨勢偵測、文體風格分析應用、隨著社群網站與物聯網的興起，應用更延伸到即時情緒意見偵測判斷與預測。

* 甚至：文本產生器，報告產生器 `Data <> Story`

* 對於人文歷史與社會科學也是很重要。e.g., `historical text mining`







---
## 基本工具箱: Linux, Git, R and Others
![Linux](linux.jpg)

- Introduce Linux environment
- Learn Linux commands
- I/O redirection and Pipeline
- Introduce server-side Linux usage (e.g., use `ssh` to communicate with a remote server)


![github](github.jpg)

- Introduce modern source code management
- Learn common `git` operations
- Setup `github` and personal portfolio page


![R](R.jpg)

```
Text Analytics with R (I)
    Rstudio environment and package management
    Basic Syntax
    Data object: Vectors, Matrices, Data Frames, and Lists
        Common functions
    Local data input/output
    Basic Data visualization
Text Analytics with R (II)
    Data scraping, sorting and merging
    String manipulation/Regular Expressions
    Dates and times
    Connecting to an external database
    Data manipulation with "dplyr"
        Tables in R
        Join
        Subset
        Advance manipulations with dplyr
    Advanced data visualization (with ggplot2)
    Building web app (with Shiny); Accessing APIs
Text Analytics with R (III)
    Statistics and Text mining packages
    Machine learning 
        Supervised Learning (Regression,Classification)
        Unsupervised Learning (Clustering,Dimension Reduction)
        Experiment and Performance evaluation
        Employing advanced algorithms (e.g., neural network)
    Parallel computing
        Hadoop
        Spark
    
    
    
```

---
## 解析流程

- Step.1 收集與準備
  - Crawling/storing the text(s)  
  - Pre-processing the text(s) <span style="color:Teal; font-weight:bold">可能就花掉妳 50% 的時間!!</span>
- Step.2 探索觀察與假設 
  - Exploratory data analysis (statistic summary/graphical representation)
  - Missing value and outlier treatment
- Step.3 自然語言處理、標注與分析
  - Natural Language Processing w/o Linguistic Analysis
  - Annotation, analysis (and back to Step.2 if necessary) 
- Step.4 預測模型
  - Predictive modeling (regression, classification, clustering,...)
  - Estimation of Performance
- Step.5 重製性報告與呈現 
  - Reproducible (and infographic) Report




---
## 相關套件

- `tm`, `openNLP`, `qdap`,`koRpus`,`zipfR`,`Rwordseg/JiebaR`, `wordnet`,`qdap`, `RTextTools`,`Rweibo`,`corpora`,`textir` `twitteR`,`facebookR`,..

The current standard for text analysis in R is the `tm` package. It provides facilities to manage text collections and to perform the most common data preparation operations prior to statistical text analysis.






---
## 本書例子

我們在本書中用的例子將以下來源為主：
-  physical sensor (**sensory description of products** obtained )
-  web and social sensor ('ptt','FB','twitter',...) 




















