
---
title: 'Benchmark timeseries forecasting exercise using `wbstats` package'
date: 2018-11-19
#permalink: /posts/2013/08/blog-post-2/
tags:
  - timeseries
  - forecasting
  - rstats
---  


I'm deliberately avoiding forecasting theories here. If you are interested in theories, plenty of materials are out there (see [Rob Hyndsman's](https://robjhyndman.com/) extensive work, for example). Instead, in this series I'll to do lot's of forecasting with many different types and shapes of real world data. I'll pick a dataset, do some analysis. Along the way I may explain why I' m doing what I'm doing; but no theories. 


### The dataset
In todays example I picked population growth dataset from Japan. I know that population in Japan is going down, so just out of curiocity I was interested in looking at historical trend and see what the future looks like in a business-as-usual situation. We will talk about some alternatives scenarios at the end.  

First we need to get the data. There're several sources, but the World Bank has the richest country sacle datasets on numerous different indicators. We could download the data from the [World Bank website](https://data.worldbank.org/) as `csv` file, then clean it up and import here. But fortunately, someone has done all of these in an R package called `wbstats` so we don't have to go through the trouble.  

Below I'm going step by step, from data preparation to forecasting and all the way to interpretation of the results.

### Preparing the data


```R
# load `wbstats` library
library(wbstats)
# we also need data wrangling package `dplyr`
library(dplyr)
```

 


```R
# import data
jppop = wb(indicator = "SP.POP.TOTL", country = "JP", startdate=1960, , enddate=2017)
```


```R
# view just first 2 rows
head(jppop)[1:2,]
```


<table>
<thead><tr><th scope=col>iso3c</th><th scope=col>date</th><th scope=col>value</th><th scope=col>indicatorID</th><th scope=col>indicator</th><th scope=col>iso2c</th><th scope=col>country</th></tr></thead>
<tbody>
	<tr><td>JPN              </td><td>2017             </td><td>126785797        </td><td>SP.POP.TOTL      </td><td>Population, total</td><td>JP               </td><td>Japan            </td></tr>
	<tr><td>JPN              </td><td>2016             </td><td>126994511        </td><td>SP.POP.TOTL      </td><td>Population, total</td><td>JP               </td><td>Japan            </td></tr>
</tbody>
</table>




```R
# from the dataframe we'll keep only 2 columns: data & value.
jppop = jppop[c(2,3)]
```


```R
# change the order of the year from descending to ascending
jppop = jppop[order(jppop$date),]
```


```R
# plot the data to see how it looks like
options(repr.plot.width = 7, repr.plot.height = 5) # set figure size
plot(jppop$value~jppop$date)
```


![](/images/2018-11-19-forecast-jp-pop/output_9_0.png)



```R
# remove the date column, we don't need it any more
jppop=jppop[c(2)]
```


```R
# convert the dataframe into a times series (ts)) object
data = ts(jppop, start =1960)
```


```R
# conver population to millions for easy visuals
data = data/1000000
```

## Forecasting


```R
# now we are in forecasting business.
# first load `fpp2` and `forecast()` package (importing just `fpp2` should work, but just in case). 
library(fpp2)
library(forecast)
library(ggplot2) # you may or may not need it, but just in case
```


```R
# plot the ts object we created, this time using autoplot() function that comes with forecast() package
options(repr.plot.width = 7, repr.plot.height = 3) # set figure size
autoplot(data) + ggtitle("Population trend in Japan") + xlab("Year") +  ylab("Millions")
```




![](/images/2018-11-19-forecast-jp-pop/output_15_1.png)


From this plot alone we can say a lot about population in Japan, some are obvious from the figure while some needs little digging. Here's a few:
- Current population in Japan is around 126 million 
- Total population has grown until around 2010 and then declining ever since
- Besides few east European nations Japan is the only developed country to experience population drop
- There are many reasons for this, but growing number of aging population and younger generation not willing to have kids are two big causes


```R
# we are doing forecasting for the year 2030 (13 years into the future from 2017, hence h=13) using five simple models
data.mean=meanf(data, h=13) # mean forecast
data.naive = naive(data, h=13) # naive forecat
data.rwf_drift = rwf(data, h=13, drift=TRUE) # random walk forecast with drift
data.spline = splinef(data, h=13) # local linear forecast
data.ets = forecast(data, h=13) # automatic ETS forecast (Exponential Smoothing)
```


```R
# view all the forecasts we just made alltogether in one figure
options(repr.plot.width = 12, repr.plot.height = 4.5) # set figure size
autoplot(data) + autolayer(data.naive, series = "Naive", PI=FALSE) + 
autolayer(data.rwf_drift, series = "RWF with drift", PI=FALSE) + 
autolayer(data.mean, series = "Mean forecast", PI=FALSE) + 
autolayer(data.spline, series = "Local linear forecast", PI=FALSE) + 
autolayer(data.ets, series = "Automatic ETS forecast", PI=FALSE)
```




![](/images/2018-11-19-forecast-jp-pop/output_18_1.png)


These forecasting results can be interpreted in many ways. First it doesn't look like RW or mean model looks any plausible, may in the longer term but not for the next 13 years period. On the other hand the other 3 forecasts look really plausible. But let's watch what all the forecast values are


```R
# find out forecast values of each method
mean = round(data.mean$mean[13])
naive = round(data.naive$mean[13])
rwf_drift = round(data.rwf_drift$mean[13])
ets = round(data.ets$mean[13])
local_linear = round(data.spline$mean[13])
t(data.frame(mean, naive, rwf_drift, ets, local_linear))
```


<table>
<tbody>
	<tr><th scope=row>mean</th><td>118</td></tr>
	<tr><th scope=row>naive</th><td>127</td></tr>
	<tr><th scope=row>rwf_drift</th><td>135</td></tr>
	<tr><th scope=row>ets</th><td>125</td></tr>
	<tr><th scope=row>local_linear</th><td>124</td></tr>
</tbody>
</table>



### Are these models any good?
In a range of scenarios and uncertainties the UN Population Prospects (www.population.un.org) meadian projection is that the population in Japan will be 121.5 million in 2030. The [World Bank](http://databank.worldbank.org/data/home.aspx) prjection is dire - 120.2 million by 2030. The nearest of those UN and WB model projections is the linear trend model that shows 124 million people. Any of these model prediction can be right, depending on how Japan responds to current population decline (Random Walk projection is probably not going to happen).

#### *Endnote:* 
*With this `wbstats` package it's really easy to make a population forecast. Just by changing `country` in the very first line of codes one can run the whole forecast (just type "US" instead of "JP", then run all and watch!).
In addition one can have unilimted fun by changing `indicator` in the same line of code!*
