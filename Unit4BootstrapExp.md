#  Unit4 HomeWork
jean Jecha  

# Bootstrap normal distribution sample 100 (simple normal)

```r
x <- rnorm(100, 22, 5)

# Simple normal dist
n <- 1000
tmpbootnrm <- numeric(n)
for(i in 1:n) {
      tmpsamp <- sample(x, 100, replace=TRUE)
      tmpbootnrm[i] <- mean(tmpsamp)
}
```


```r
summary(tmpbootnrm)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   21.57   22.83   23.13   23.14   23.46   24.72
```

```r
hist(tmpbootnrm)
```

![](Unit4BootstrapExp_files/figure-html/tmphist-1.png)<!-- -->

# Bootstrap normal distribution of size 50 (parametric confidence interval)

```r
x <- rnorm(50, 22, 5)
xbar <- mean(x)

## Find the pivot t-interval
bootnorm <- numeric(1000)
for (i in 1:1000){
      bootsamp <- sample(x,size=50,replace=TRUE)
      bootmean = mean(bootsamp)
      bootsd = sd(bootsamp)
      tpivot = (bootmean - xbar)/(bootsd/sqrt(50))
      bootnorm[i] <- tpivot
}
```

showing inter quartile

```r
#get numbers at the 2.5% and 97.5% quantile 
quant <- quantile(bootnorm, c(0.025, 0.975)) 

quant
```

```
##      2.5%     97.5% 
## -1.996105  1.977838
```


# Exponential distribution for sample size 50

```r
n <- 50 
expmean50 <- numeric(1000)

for (i in 1:1000){
      x <- exp(n)
      expmean50[i] <- mean(x)
}
mean(expmean50)
```

```
## [1] 5.184706e+21
```

# Exponential distribution for sample size 75

```r
n <- 75 
expmean75 <- numeric(1000)

for (i in 1:1000){
      x <- exp(n)
      expmean75[i] <- mean(x)
}
mean(expmean75)
```

```
## [1] 3.733242e+32
```

