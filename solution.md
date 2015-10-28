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

{% exercise %}
HW5.R: For each word in https://ceiba.ntu.edu.tw/course/6d0f76/content/Word_Emotion_DT.csv
aggregate the mean scores of each word.

#download.file(url='https://ceiba.ntu.edu.tw/course/6d0f76/content/Word_Emotion_DT.csv',destfile='Word_Emotion_DT.csv',method='wget')

#df=read.csv(file='Word_Emotion_DT.csv',header=FALSE)

#head(df)

#library(data.table)

#DT=data.table(df)

#DT[,j=.(mean=mean(V1)),by=V2]

{% validation %}
{% solution %}
{% endexercise %}

