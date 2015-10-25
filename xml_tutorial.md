# XML Tutorial
---

基本知識：學會如何編輯(edit)，剖析(parse)，驗證 (validate) 與轉換 (transform) XML 標記文件。

- 剖析(parse):
- 驗證 (validate) : against certain DTD/ Schema(xsl)


## 例子
老莎的十四行

```xml
<?xml version="1.0"?>
<!DOCTYPE sonnet SYSTEM "sonnet.dtd">
<sonnet type="Shakespearean">
  <author>
    <last-name>Shakespeare</last-name>
    <first-name>William</first-name>
    <nationality>British</nationality>
    <year-of-birth>1564</year-of-birth>
    <year-of-death>1616</year-of-death>
  </author>
  <title>Sonnet 130</title>
  <lines>
    <line>My mistress' eyes are nothing like the sun,</line>
    <line>Coral is far more red than her lips red.</line>
    <line>If snow be white, why then her breasts are dun,</line>
    <line>If hairs be wires, black wires grow on her head.</line>
    <line>I have seen roses damasked, red and white,</line>
    <line>But no such roses see I in her cheeks.</line>
    <line>And in some perfumes is there more delight</line>
    <line>Than in the breath that from my mistress reeks.</line>
    <line>I love to hear her speak, yet well I know</line>
    <line>That music hath a far more pleasing sound.</line>
    <line>I grant I never saw a goddess go,</line>
    <line>My mistress when she walks, treads on the ground.</line>
    <line>And yet, by Heaven, I think my love as rare</line>
    <line>As any she belied with false compare.</line>
  </lines>
</sonnet>
```

## 剖析器

- XML parser 用來 parse and validate XML。                
- 免費的有很多，可用 [Apache Software Foundation’s Xerces-Java XML parser](http://xerces.apache.org/xerces2-j/)。因為可以從指令列使用。
- 直接用 [`GATE`](https://gate.ac.uk/)







---
## 參考

- [W3School](http://www.w3schools.com) 有許多練習
- (Tidwell 2002). Introduction to XML .
- (Wilcock, 2009). Linguistic annotation and text analytics.