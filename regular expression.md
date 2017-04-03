# Regular Expression \(regex\)

---

一種確認文字模式的符號標記法。主要利用 **grep 來**完成。\(主要用法見 `tldr grep`\)

學習 regex 也可說是對「文字資料」學習一種新的解析能力。



```
$grep -i 愛 *.* | love.txt
```







### Meta-characters

#### 定錨 anchor: 開頭 \(^\) 結尾 \($\)



#### 方括弧

```
$grep -h '[mk]ill' corpus*.txt
```



#### 否定

```
$grep -h '[^mk]ill' corpus*.txt
```



## 量詞 quantifiers

#### ? \(0 或1\) Match an Element Zero Times or One Time

```

```

#### \* \(0 或 多\) Match an Element Zero or More Times

```

```

#### ＋ \(1 或 多\) Match an Element One or More Times

```

```









