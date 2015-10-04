# 習題解答


HW1

\#d00142002
library(jiebaR)
words='中秋節'
words_vector=worker()<=words
t=table(words_vector)
write.table(x=t,file='d00142002.csv',row.names=FALSE,col.names=FALSE)

