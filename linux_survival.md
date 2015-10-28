# Linux 指令列存活指令

場景：

想像一下你手邊拿到一份有 5 GB 大的 `mydata.csv` 檔。檔案中有超過一千萬列 (rows) 的詞項與 40 行 (column) 的各項變量資料。你現在的任務只是要對於其中第四行所有數值做加重。寫 R 程式？載入與存取 SQL 資料庫？最有效率的方式還是利用指令列工具。

```bash
$cat mydata.csv | awk -F "|" '{ sum += $4 } END { printf "%.2f\n", sum }'
```
上面這一行大概花不到兩分鐘就搞定這件事。想做一個資料科學家，不學行嗎？


------
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



## 文本處理常用

- echo

```bash
$echo "語言學很重要" > note.txt
```
- cat（依標準輸出顯示檔案內容）
- head

```bash
$head -n 3 data.csv
```
- tail
- more（看檔案內容，滿頁暫停按 space 鍵繼續，按 q 結束）
- less（同上，但允許游標鍵上下捲動對內容進行瀏覽）

- wc （計算字數、行數、字元數）

```bash
$wc mydata.csv
$wc -l mydata.csv
```
- grep: 可以利用**正則表示法** (參考本書附錄) 來搜尋文本中的特定模式。有許多參數可設定。

```bash
$grep -i -A 1 -B 10  work mydata.csv | head -n 5
```

- sed
可用來取代

```bash
$sed -e 's/keke/科科/g' mydata.csv > mydata2.csv
```

> [注意]  轉不同系統處理的文件時常用這個指令！

因為不同系統對於「換行字元」有不同的編碼方式。
Windows 系統用了`\r\n`，亦即「回車」 CR (carriage return) 與 「換行」LF (line feed) 來表達換行。在編輯器裡會在一行的節尾看到 `^M`，那就是`\r\n`。蘋果每行的結尾則是用 CR `\r`, linux/unix 用 LF `\n`。[^1]


造成的一個後果是，Unix/Mac系統下的文件在 Windows 裡打開的話，所有文字會變成一行；而 Windows 裡的文件在 Unix/Mac 下打開的話，在每行的結尾可能會多出一個`^M`符號。


```bash
$sed -e 's/\^M//g' winfile.in > linuxfile.out
# sed -e 's/^M//g' testfile > testfile.out 也可以，但是要用 ctrl-v ctrl-m 來打出^ 
```

- sort 與 uniq



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
1. 比較並顯示兩個詞表的差異。

```bash
$comm <(sort lex1.txt) <(sort lex2.txt)
動人心弦
		好
	正
	水喔
		漂亮
精湛
美好
美麗
豐富

```

2.產生一個新詞表，其中只含有比較之後在 lex1.txt 但沒出現在 lex2.txt 的詞（可想成用後者過濾前者）。[^2] 



```bash
$comm -2 -3 <(sort lex1.txt) <(sort lex2.txt) > lex3.txt
$cat lex3.txt
動人心弦
精湛
美好
美麗
豐富
```




附註：

[^1] 參見 https://en.wikipedia.org/wiki/Newline

[^2] 如果有安裝 `vim` 的進階使用者，可看看更炫的 `vim -d` lex1.txt lex2.txt。
