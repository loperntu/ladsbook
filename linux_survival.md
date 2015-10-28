# Linux 指令列存活指令



## 目錄和檔案處理
- pwd（顯示目前工作目錄）
- ls（列出當前目錄下的內容）
- cd（更換工作忙碌）
- cp（拷貝檔案及目錄）
- mv（移動或重新命名檔案）
- mkdir（建立目錄）
- rm（刪除檔案或目錄）

```bash
$rm -rf non-empty_dir
```

## 輸入輸出與管線



## 文本處理

- echo

```bash
$echo "語言學很重要" > note.txt
```
- cat（依標準輸出顯示檔案內容）
- head
- tail
- more（看檔案內容，滿頁暫停按 space 鍵繼續，按 q 結束）
- less（同上，但允許游標鍵上下捲動對內容進行瀏覽）

## 比較詞表

- diff
- sdiff
- comm （需要先將文件排序過）
- cmp

假定你有兩份詞表 lex1.txt 和 lex2.txt,分別長這樣。

```bash
$cat lex1.txt
動人心弦
精湛
美麗
豐富
美好
漂亮
好

$cat lex2.txt
好
水喔
漂亮
正

```

想要
1. 比較兩個詞表，並且同時產生一個新詞表，其中只含有比較之後在 lex1.txt 但沒出現在 lex2.txt 的詞（可想成用後者過濾前者）。[^1] 


```bash
$comm -2 -3 <(sort lex1.txt) <(sort lex2.txt) > lex3.txt
$cat lex3.txt
動人心弦
精湛
美好
美麗
豐富
```

2.






附註：

[^1] 如果有安裝 `vim` 的進階使用者，可看看更炫的 `vim -d` lex1.txt lex2.txt。
