# 貝氏網路

- A network can be as simple as two variables that relate to each other, or it can contain thousands of variables, as in, for instance, research into how genes interact.


網路模式可以解決的應用問題 (Stuhl, 2015)

- Automatically finding meaningful patterns among variables;
- Getting accurate measures of variables' strengths;
- Screening large numbers of variables quickly, for data mining;
- Developing models of cause and effect (in the right circumstances);
- Incorporating expert judgment into data-driven models;
- Solving problems in conditional probability.


#### 素樸貝氏 Naive Bayes

```
# Import required library
library(e1071)

# Fitting model
fit <- naiveBayes(y_train ~ ., data = x)
summary(fit)

# Predict Output
predicted <- predict(fit, x_test)

```


