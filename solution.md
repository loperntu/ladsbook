# 習題解答

HW1.R
```{r}
library(jiebaR)
worker()<='中秋節'
```
---
HW2.R
```{r}
table(words_vector)
```
---
HW3.sh
```{bash}
cat 1001_chinatimes.txt | Rscript segmentation.R | tr ' ' '\n' | sort | uniq -c | sort -nr
```
---
HW4.R

{% exercise %}
HW4: How many times do I and like co-occur?
{% initial %}
{% solution %}
X[1,2]
{% validation %}

{% endexercise %}


```{r}
X=rbind(I,like,enjoy,deep,learning,NLP,flying,period)
X[1,2]
sum(X[1,]
sum(X[2,]/2
```
---
HW5.R

For each word in https://ceiba.ntu.edu.tw/course/6d0f76/content/Word_Emotion_DT.csv

aggregate the mean scores of each word.


good	2.0

eat		1.6

cold	3.3
