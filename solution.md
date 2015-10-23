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

{% exercise %}
HW3.sh: Segment 1001_chinatimes.txt and find the most frequent words.
{% validation %}
{% solution %}
cat 1001_chinatimes.txt | Rscript segmentation.R | tr ' ' '\n' | sort | uniq -c | sort -nr
{% endexercise %}

{% exercise %}
HW4.R: How many times do I and like co-occur?
{% initial %}
{% solution %}
X[1,2]
{% validation %}
{% endexercise %}

{% exercise %}
HW5.R: For each word in https://ceiba.ntu.edu.tw/course/6d0f76/content/Word_Emotion_DT.csv
aggregate the mean scores of each word.
{% validation %}
{% solution %}
good	2.0
eat 1.6
cold	3.3
{% endexercise %}

{% exercise %}
{% validation %}
{% solution %}
{% endexercise %}
