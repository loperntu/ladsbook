# 習題解答


HW1

\#d00142002.R

library(jiebaR)

words='中秋節'

words_vector=worker()<=words

write.table(x=t,file='d00142002.txt',row.names=FALSE,col.names=FALSE)


HW2

\#d00142002.sh

sort d00142002.txt | uniq -c | sort > d00142002.txt