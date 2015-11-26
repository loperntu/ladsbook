# 習題解答

baseline.R
```{r}
library(package='jiebaR')

# training
train=read.csv(file='train.csv',stringsAsFactors=FALSE)
keywords=list()
for(i in 1:10){
    words=worker()<=paste(train[train$category==i,]$news,collapse='')
    
    keywords[[i]]=names(sort(table(words),decreasing=T))[1:100]
}

categorize=function(words){
    output=1
    max=0
    for(i in 1:10){
        score=0
        for(word in words){
            if(word %in% keywords[[i]])score=score+1
        }
        if(score>max){
            max=score
            output=i
        }
    }
    return(output)
}

# testing
test=read.csv('test.csv',stringsAsFactors=F)
df=data.frame(id=NA,category=NA)
for(i in 1:nrow(test)){
    words=worker()<=test$news[i]
    df[i,]=c(test$id[i],categorize(words))
}
write.csv(df,'baseline900.csv',quote=FALSE,row.names=F)
```

HW1.R: Segment [1001_chinatimes.txt](https://ceiba.ntu.edu.tw/course/6d0f76/content/1001_chinatimes.txt) and put the words in a vector.
```{r}
txt=scan('1001_chinatimes.txt',what='char')
library(jiebaR)
word_vecotr=worker()<=txt
```

HW2.R: Find the most frequent words in [1001_chinatimes.txt](https://ceiba.ntu.edu.tw/course/6d0f76/content/1001_chinatimes.txt)
```{r}
table(word_vector)
```

HW3.sh: Segment [1001_chinatimes.txt](https://ceiba.ntu.edu.tw/course/6d0f76/content/1001_chinatimes.txt) and find the most frequent words.
```
cat 1001_chinatimes.txt | Rscript segmentation.R | tr ' ' '\n' | sort | uniq -c | sort -nr
```

HW4.R: How many times do the word I and like co-occur?
```{r}
X=matrix(c(0,2,1,0,0,0,0),
         c(2,0,0,1,0,1,0,0))
colnames(X)=c('I','like','enjoy','deep','leanring','NLP','flying','.')
X[1,2]
```

# HW7
Segment [Ma_Ying_Ju](http://dropbox.com/sh/pbbsla84bq6o678/AACtO1WjaMIxVh97eyWO81yNa)'s talks with POS tagging.
```{r}
lines=vector()
path='Ma_Ying_Ju/'
for(filename in list.files(path)){
  con=paste(path,filename,sep='')
  lines=c(lines,readLines(con))
}

library(jiebaR)
word_vector=worker(type='tag')=lines
tag_vector=names(word_vector)
```
1. Get all nouns by grep() and build a frequent table of noun tags (n 587, nr 20, nr 1, ...) 30%
```{r}
nountag_vector=grep(pattern='n',x=tag_vector,value=T)
sorted_tags=sort(table(nountag_vector),decreasing=T)
```
2. Build a frequency table of noun list. (經濟 60, 台灣 42..) 30% 
```{r}
index_vector=grep(pattern='n',x=tag_vector,value=F)
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
