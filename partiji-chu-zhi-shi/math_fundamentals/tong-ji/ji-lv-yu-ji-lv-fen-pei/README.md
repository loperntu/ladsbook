# 機率與機率分佈

* 事件
* 機率
* 隨機變數
* 機率分佈











* **機率密度函數：**隨機變數值 $$x$$ 和機率 $$\mathcal{P}$$ 之間的函數關係。 







### 常態\(機率\)分佈 normal distribution \(a.k.a 高斯分佈 Gaussian distribution\)



*     

$$
P(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\left[\frac{(x - \mu)^2}{2\sigma^2}  \right]}
$$

* $$\sigma$$ refers to the standard deviation. 
* $$\mu$$ refers to the mean. 
* $$e$$ is a constant, respectively, the base of the natural log system and approximately equals to 2.718. 
* $$\pi$$ a constant with an approximate value of $$\frac{22}{7}$$ or 3.1416. 
* $$x$$ refers to the value of the random variable.



```text
rnorm(n=10) 
[1] -0.48200811  1.02070719  0.09263650  0.07460888  1.75003405  
0.22843413 [7] -0.11792523  0.39054810 -0.35487301 -1.82808605
```



### Poisson Distribution

$$
P(x) = \frac{\mu^{x}e^{-\mu}}{x!}
$$

* 針對計數資料 count data
* trial 次數很多 \(n 很大\)， 事件發生機率（P）很小時的二項分布。 











