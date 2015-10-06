# 習題解答


<<<<<<< HEAD
=======
HW1

\#d00142002.R

library(jiebaR)

words='中秋節'

words_vector=worker()<=words

write.table(x=t,file='d00142002.txt',row.names=FALSE,col.names=FALSE)


HW2

\#d00142002.sh

sort d00142002.txt | uniq -c | sort > d00142002.txt

>>>>>>> origin/master

{% exercise %}
Define a variable `x` equal to 10.
{% initial %}
var x =
{% solution %}
var x = 10;
{% validation %}
assert(x == 10);
{% context %}
// This is context code available everywhere
// The user will be able to call magicFunc in his code
function magicFunc() {
    return 3;
}
<<<<<<< HEAD
{% endexercise %}
=======
{% endexercise %}
>>>>>>> origin/master
