# 導論

## 資料科學是什麼？資料科學家會什麼？

* To retrieve, transform, explore and model data as well as interprete and communicate results in a compelling way. 
* Be able to gain insights into your data and solve real-world problems with programming languages \(e.g., R/Python\) as well work with big data technology \(Hadoop, Spark\). 
* 'number guys' vs 'text miners'.

## 語言與文本分析

* 文本四處都在，特別是網路。文本資料來源：網頁，新聞，網誌，電郵，社交媒體等等。（reviews, postings, tweets, blogs, news, articles, responses to surveys, advertisements, product descriptions, scholarly papers, emails, comments collected for insurance, retail, health care and research \(to name a few\)。
* 文本資料的構成：以自然語言為主，常常伴隨各種表情符號，以及其他的多媒體素材。
* 語言與文本分析的用意，就是運用語言學與文本分析的知識與技術，將文本**資料**\(data\)中蘊含的**訊息**\(information\)發掘出來，進一步轉化成**知識**\(knowledge\)，應用在各個領域。
* 文本很大程度的反映了語言使用，而中文有其獨特的特性，因此需要語言學的知識才能很好的分析。

## Data Science and Text Analytics

資料科學家的工作，可以視為是一個探索、預測與解讀資料意義的互動歷程。而語言分析的工作，在了解文本資料的語意與情緒表現上是重要的關鍵。本課程結合了目前統計程式設計與自然語言處理技術，以較為簡潔容易入門的設計與實際操作導引，希望可以讓毫無相關程式學習基礎的學生在本課程的帶領下，達到以下的學習目標：

1. 了解結構與非結構性資料的特性與預處理工作,特別是針對中文文本中呈現的語言特性的處理方法。
2. 了解中文的語言特性與文本解析 \(text analytics\) 的基本概念。
3. 選擇適當的變數與特徵並加以合理調製,對之進行描述統計與視覺探勘,針對不同的問題點與數據類型,找出適當的圖形表達與統計分析。
4. 學習簡易的自然語言處理與機器學習預測模式,並應用在自己關心的領域。

## 文本是什麼 Text Representation

* 文件和文本 document and text
* structured, semi-structured and unstructured data
* doc, csv, pdf, xml, html, markdown....

## 文本挖掘/文本解析 \(Text Analytics/Text Mining\)

* `KDD (Knowledge Discovery in Database)` + `Data Mining`: 著重在如何從結構化的數據中挖掘出新的知識； `Text mining` + `NLP (Natural Language Processing)`則著重在如何從非結構化或半結構化的數據中挖掘出新的知識。
* 文本挖掘可以被定義成`以自動化或半自動化文本處理方法，挖掘文本中的知識的歷程`。資料處理的層次來說，涉及如何把非結構性的數據轉化成結構化的數據，以方便機器學習分析與判讀。
* You do not need to have **big data** to do text analytics. The methods work with large, medium and small datasets.
* 通常的應用涉及了文本分類與叢聚、模式與趨勢偵測、文體風格分析應用、隨著社群網站與物聯網的興起，應用更延伸到即時情緒意見偵測判斷與預測。 甚至：文本產生器，報告產生器。
* 對於人文歷史與社會科學也是很重要。e.g., `historical text mining`
* 文本分析的新亮點，在於各種 transformation \(`text2number`, `text2speech`,`text2score`, `text2image`, 與反向操作，etc\)
* Story telling and Narrative

## 涉及學門間的關係

![Re](../.gitbook/assets/lads.png)

## 基本工具箱: Linux, Git, R and Others

![Linux](../.gitbook/assets/linux.jpg)

* Introduce Linux environment
* Learn Linux commands
* I/O redirection and Pipeline
* Introduce server-side Linux usage \(e.g., use `ssh` to communicate with a remote server\)

![github](../.gitbook/assets/github.jpg)

* Introduce modern source code management
* Learn common `git` operations
* Setup `github` and personal portfolio page

![R](../.gitbook/assets/r.jpg)

```text
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

## 解析流程

* Step.1 收集與準備
  * Crawling/storing the text\(s\)  
  * Pre-processing the text\(s\) 可能就花掉妳 50% 的時間!!
* Step.2 探索觀察與假設 
  * Exploratory data analysis \(statistic summary/graphical representation\)
  * Missing value and outlier treatment
* Step.3 自然語言處理、標注與分析
  * Natural Language Processing w/o Linguistic Analysis
  * Annotation, analysis \(and back to Step.2 if necessary\) 
* Step.4 預測模型建立與評估
  * Predictive modeling \(regression, classification, clustering,...\)
  * Estimation of Performance
* Step.5 重製性報告與呈現 
  * Reproducible \(and infographic\) Report
  * Web app

這個圖  說出 \(之前的!\) 文本挖掘作法流程 ![](../.gitbook/assets/tm101.jpg)

## 相關套件

* `tm`, `openNLP`, `qdap`,`koRpus`,`zipfR`,`Rwordseg/JiebaR`, `wordnet`,`qdap`, `RTextTools`,`languageR`,`Rweibo`,`corpora`,`textir` `twitteR`,`facebookR`,..

The current standard for text analysis in R is the `tm` package. It provides facilities to manage text collections and to perform the most common data preparation operations prior to statistical text analysis.

## 相關網路服務

愈來愈多的文本解析的線上服務

* [Calais](http://www.opencalais.com): 回傳 `專名`, `主題`, `事件`, `關係`, 與 `社會標籤`。
* [BosonNLP](introductionmd.md)

## 相關學術會議

* Linguistic Annotation Workshops
* [Annual Text Analytics Summits](http://www.textanalyticsnews.com) 

## 本書例子

物聯網時代，資料來源的大宗除了網路之外，可能會是感測器。我們在本書中用的例子將以下來源為主：

* 網路文本 web
* 實體感測器：即時紀錄語音轉文本後的各種訊息。physical sensor \(**sensory description** obtained by rating a set of products/events/ according to a list of sensory attributes.\)
* 各種社會媒體作為社會感測器：social sensor \('ptt','FB','twitter',...\) 

 出處：[https://manoharswamynathan.files.wordpress.com/2015/04/r-text-mining-001.jpg](https://manoharswamynathan.files.wordpress.com/2015/04/r-text-mining-001.jpg)

 新工作類型興起 陳良基：矽谷story telling年薪近500萬 [http://news.ltn.com.tw/news/life/breakingnews/1841618](http://news.ltn.com.tw/news/life/breakingnews/1841618)

