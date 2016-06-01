# BootstrapUnit4HomeWork


# R Markdown



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


