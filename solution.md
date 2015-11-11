# 習題解答

# HW7
Segment [Ma_Ying_Ju](dropbox.com/sh/pbbsla84bq6o678/AACtO1WjaMIxVh97eyWO81yNa)'s talks with POS tagging.
```{r}
library(jiebaR)
lines=readLines(con='MYJ1030101.txt')
word_vector=worker('tag')lines
pos_vector=names(word_vector)
```
1. Get all nouns by grep() and build a frequent table of noun tags (n 587, nr 20, nr 1, ...) 30%
```{r}
nountag_vector=grep(pattern='n',x=pos_vector,value=T)
sorted_tags=sort(table(nountag_vector),decreasing=T)
```
2. Build a frequency table of noun list. (經濟 60, 台灣 42..) 30% 
```{r}
index_vector=grep(pattern='n',x=pos_vector,value=F)
pos_vector[index_vector]
sorted_nouns=sort(table(word_vector[index_vector]),decreasing=T)
```
3. Draw appropriate figures to show the above results. 40%
```{r}
barplot(sorted_tags)
barplot(sorted_nouns)
```

# HW6-1.R (40%)
Please explain your following figures for https://ceiba.ntu.edu.tw/course/6d0f76/content/Word_Emotion_UTF8.csv
1. barplot, hist, plot, and boxplot the distribution of scores for eat, with appropriate vector or matrix.
2. produce summary of eat by min, quantile, median, mean, and max.

# HW6-2.R (60%)
Please read something about [probability distribution](http://books.google.com.tw/books?id=UvWkIg5E4foC):
![](http://upload.wikimedia.org/wikipedia/commons/thumb/1/12/Dice_Distribution_%28bar%29.svg/320px-Dice_Distribution_%28bar%29.svg.png)

Then randomly generate more than 100 data points for the [normal distribution](http://en.wikipedia.org/wiki/Normal_distribution) with mean μ=0 and sd σ=1, e.g. rnorm(n=100)
![](http://upload.wikimedia.org/wikipedia/commons/a/a9/Empirical_Rule.PNG)

1. Produce quantiles corresponding to the given probabilities of 50%, 84%, 97.5%, and 99.85%
2. Check the above quantiles by using qnorm(p) only.
3. How many data points are less than 0, 1, 2 and 3 respectively? And the corresponding percentages?
4. Calculate the mean for all data points.

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
