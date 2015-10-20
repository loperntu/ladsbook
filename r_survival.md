# R 存活知識

> The R survival guide for LADs (Linguistic Analysis and Data Science) 

---
(必修)
## 三分鐘上手指令

```{r}
head(iris)
str(iris)
summary(iris)
plot(iris)
```

### 變數、資料類型與基本運算
variables, data types and basic arithmetic

- 變數與賦值
    - 變數命名大小寫有區別 (x 和 X 不一樣)
    - 賦值算子 `<-`，`=` 貌似可以，但 R 官方文件強調不該使用，在某些地方會失效。

```{r}
x <- 38
x
```


- 基本算術運算

    加減乘除、次方、平方根、商數與餘數、指數與對數、等等。

```{r}
20^3
exp(20)
log(20)
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


## 資料結構 



### 向量 Vector

- 利用 `c()` 建立向量，向量元素必須是同個資料類型，不然就會按照 *character > complex > numeric > integer > logical* 進行類型迫轉 (type coersion) 

```

```

### 矩陣 Matrix
### 因子 Factor
### 資料框架 Data Frame
### 列表 List 


## 資料處理流程邏輯
### 條件與邏輯判斷式 Conditionals and Control Flow


### 迴圈結構 Loops and the `apply` family

##



## 繪圖與資料視覺化

## 自訂函式










## 資料統計
---
(增效小訣竅)

- `crtl + l` 清除 console 畫面
- `rm(list = ls())` 清楚 workspace 所有物件
- ? 看對於內建資料或是指令的輔助說明，如 `?iris`, `?rep` 


---
(選修)

## 資料科學的報告與表達

## 機器學習

## 大數據處理




