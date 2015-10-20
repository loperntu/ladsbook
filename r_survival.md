# R 存活知識

> The R survival guide for LADs (Linguistic Analysis and Data Science) 

---
(必修)
## 三分鐘上手指令

```{r}
> head(iris)
> str(iris)
> summary(iris)
> plot(iris)
```

### 變數、資料類型與基本運算
variables, data types and basic arithmetic

- 變數與賦值
    - 變數命名大小寫有區別 (x 和 X 不一樣)
    - 賦值算子 `<-`，`=` 貌似可以，但 R 官方文件強調不該使用，在某些地方會失效。

```{r}
> x <- 38
> x
```


- 基本算術運算

    加減乘除、次方、平方根、商數與餘數、指數與對數、等等。

```{r}
> 20^3
> exp(20)
> log(20)
```


* 資料類型包含以下五種，可用 `class()` 函數判斷

    - character：文字字串，用 "" 包起來，ex："test"
    - numeric：實數
    - integer：整數
    - complex：複數
    - logical：True 或 False

`NA` 是保留字，邏輯常數

```
> NA <-2
Error in NA <- 2 : (do_set) 賦值公式左側不正確
> NULL <-2
Error in NULL <- 2 : (do_set) 賦值公式左側不正確
```

- 資料類型之間的轉換可透過不同內建函式


- 文本資料


## 資料匯入與匯出

```{r}
> mydata <- read.table()
```

- 文件編碼與轉碼

```{r}


```

- 匯出檔案

    - 用 `write.table()` 輸出 csv

```{r}
> mydata <- rivers 
# rivers 是 R 內建的資料集。
> write.table(mydata, file = "rivers.csv", sep = ",")
```


## 資料結構 

- 相關的內建函式不外乎**建立、查詢、修改資料**。

### 向量 Vector

- 利用 `c()` 建立向量，向量元素必須是同個資料類型，不然就會按照 *character > complex > numeric > integer > logical* 進行資料類型迫轉 (type coersion) 

```

```



### 陣列 Array 與矩陣 Matrix

- 陣列 (array) 可視為多維度的向量變數，跟向量一樣，所有陣列元素的資料類型必須一致。
- **當陣列是 2 維時** 稱作矩陣 (matrix)

```{r}
> matrix(c(1:9), nrow = 3, ncol =3) 
# 預設是按照 column 填入資料
```
### 因子 Factor
- 把向量中的元素做「分類」

```{r}
> x <- c(5,6,7,7,8,3,5,2)
> x
[1] 5 6 7 7 8 3 5 2
> factor(x)
[1] 5 6 7 7 8 3 5 2
Levels: 2 3 5 6 7 8

```


### 資料框 Data Frame
### 列表 List 

- 列表可以包含不同資料類型的資料

## 資料處理流程邏輯
### 條件與邏輯判斷式 Conditionals and Control Flow


### 迴圈結構 Loops and the `apply` family


---
## 資料探索分析

- 資料探索分析 (exploratory data analysis) 是資料科學分析歷程很重要的一環，目的是適當的來來回回檢視資料以取得合理的假說。
- 涉及到 **資料操控、資料視覺化技巧與統計分析**。






## 資料操控 
資料操控 (data manipulation) 是 **資料探索分析** (exploratory data analysis) 所需要的重要技能之一。包括對於資料的：
- 重新編碼
- 資料變形
- 資料合併與分割


## 繪圖與資料視覺化




## 資料統計
---
(增效小訣竅)

- `crtl + l` 清除 console 畫面
- `rm(list = ls())` 清楚 workspace 所有物件
- ? 看對於內建資料或是指令的輔助說明，如 `?iris`, `?rep` 



## 自訂函式

---
(選修)

## 資料科學的報告與表達

## 機器學習

## 大數據處理




