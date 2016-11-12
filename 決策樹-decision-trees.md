### 決策樹 Decesion Tree

```
# Import required library
library(rpart)

# Fitting model (growing tree)
fit <- rpart(y_train ~ ., data = x, method="class")
summary(fit)

# Predict Output
predicted <- predict(fit, x_test)
```


