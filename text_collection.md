# 文本收集

- 建立文本語料庫「前處理」的第一步。
- 數據來源很多元，如果自己有的話很容易。

```r
# 工作路徑
# windows example
setwd("C:\\Users\\shukai\\Documents\\corpus")
# linux/MacOS example
setwd("~/Dropbox/Linguistic.Analysis.and.Data.Science/corpus")

# get listing of .txt files in directory
filenames <- list.files(getwd(), pattern="*.txt")

# read files into a character vector
files <- lapply(filenames, readLines)

```

- 如果需要從網路抓取（大半部分的情形）











---
## 網路爬蟲服務

- 蟲數據 (chong data)
- Kimonolab
    



