# 習題解答

{% exercise %}
HW1.R: Segment 1001_chinatimes.txt
{% validation %}
{% solution %}
library(jiebaR)
worker()<=txt
{% endexercise %}

{% exercise %}
HW2.R: Find the most frequent words in 1001_chinatimes.txt
{% validation %}
{% solution %}
table(words_vector)
{% endexercise %}

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

# HW5-1.R
For each word in https://ceiba.ntu.edu.tw/course/6d0f76/content/Word_Emotion_DT.csv
aggregate the mean scores of each word.
```{r}
download.file(url='https://ceiba.ntu.edu.tw/course/6d0f76/content/Word_Emotion_DT.csv',destfile='Word_Emotion_DT.csv',method='wget')
df=read.csv(file='Word_Emotion_DT.csv',header=FALSE)
head(x=df)

library(package=data.table)
DT=data.table(df)
DT[,j=mean(V1),by=V2]
```

# HW6-1.R
Please explain your following figures from https://ceiba.ntu.edu.tw/course/6d0f76/content/Word_Emotion_UTF8.csv
1. barplot, hist, plot, and boxplot the distribution of scores for eat, with appropriate vector or matrix.
2. produce summary of eat by min, quantile, median, mean, and max.


# HW6-2.R
Probability Distribution
1. Randomly generate more than 100 data points for the normal distribution with μ=0 and σ=1, e.g. rnorm(n=100)  

  a. How many data points are less than 0, 1, 2 and 3 respectively? And the corresponding percentages?
  b. Produces quantiles corresponding to the given probabilities of 50%, 84%, 97.5%, and 99.85%
  c. Calculate the mean for all data points.

2. Produces quantiles corresponding to the given probabilities of 50%, 84%, 97.5%, and 99.85% in normal distribution with μ=0 and σ=1 (Hint: qnorm(p))
