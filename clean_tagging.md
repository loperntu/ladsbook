# 文本清理與自動訊息標注



## 文本清理
Cleaning up texts (Stuhl, 2105)


- stop words (such as the, of, and, a, to, and so on) must be removed. These words do not contain any meanings that will help the analysis, and they can occur so frequently that that they swamp all the words that do have meaning.
- words must be made regular, by a process sometimes called **stemming**.
- Spelling errors need to be corrected using a dictionary. Plurals must be singularized. Idiomatic expressions need to be resolved. Tenses need to be made uniform so that the same word does not reappear many times with minor variations.
– **Lemmatization** is a special type of stemming that regularizes words while trying to figure out their part of speech. How words get reduced to a stem may differ depending on how the words are used. For instance, the noun ‘moped’ should not be stemmed into the form ‘mope’, while the verb ‘moped’ should.
- With text that people have typed in themselves online, we will need to remove all the nonsensical or obviously non-useful comments, such as ‘nothing’ or ‘what?’ or ‘no comment’ or ‘fjjfjfjfjfjfj’, that we find appearing in commentary. Phrases such as these make up a surprisingly large percentage of online responses.

```
噪訊的定義，取決於妳的研究目的。
```

- Depending on the stemming program, we may also look for word pairs or larger groups of words (eg ‘not good’ or ‘not bad’ or ‘South Gas Works’). We will discuss this process directly below.
    Programs may remove infrequent words. Some have a setting you can adjust to screen words based on how often they appear. For instance, the 100 or so words that made up the entire table excerpted in Figure 2.1 all appeared in at least 1 per cent of all individual documents. Eliminating infrequent words helps reduce the overall analytical burden considerably.

