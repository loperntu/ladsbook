# 文本迴歸預測

Text regression using `tm` and `glmnet`










### 線性迴歸 R

```
# Load Train and Test datasets
# Identify feature and response variable(s);values must be numeric

x_train <- input_variables_values_training_datasets 
y_train <- target_variables_values_training_datasets 
x_test <- input_variables_values_test_datasets
x <- cbind(x_train, y_train)

# Train the model using the training sets and check score
linear <- lm(y_train ~ ., data = x)
summary(linear)
# Predict Output
predicted <- predict(linear,x_test)
```


### Logistic 迴歸 R

```
x <- cbind(x_train,y_train)

# Train the model using the training sets and check score
logistic <- glm(y_train ~ ., data = x,family='binomial')
summary(logistic)
# Predict Output
predicted <- predict(logistic,x_test)


```












