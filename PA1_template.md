# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

This code loads the csv file:

```r
data <- read.csv("activity.csv")
```



## What is mean total number of steps taken per day?

First we calculate the total number of steps per day ignoring the NA values:

```r
spd <- sapply(split(data$steps, data$date, drop = TRUE), sum)
```


Now the histogram is drawn using the ggplot2 library

```r
library(ggplot2)
qplot(spd, xlab = "Total number of steps per day", breaks = seq(0, 20000, by = 1000))
```

![plot of chunk histogram](figure/histogram.png) 


This code calculate the mean and the median for the daily totals:

```r
mean.spd <- format(mean(spd, na.rm = TRUE), scientific = FALSE)
median.spd <- format(median(spd, na.rm = TRUE), scientific = FALSE)
```


The mean for the total number of steps per day is 10766 steps and the median
is 10765 steps


## What is the average daily activity pattern?




## Imputing missing values




## Are there differences in activity patterns between weekdays and weekends?


