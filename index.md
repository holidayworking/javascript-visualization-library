---
title       : JavaScript の可視化ライブラリ達
subtitle    : BBMTG
author      : holidayworking
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap, mathjax]   # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

$ \pi $

---

## 本日紹介するライブラリ達

* Polychart2.js
* Morris.js
* NVD3
* xCharts
* HighCharts
* Rickshaw

---

## Polychart2.js

Polychart2.js is an easy-to-use yet powerful JavaScript graphing library. It takes many ideas from the Grammar of Graphics and the R library ggplot2, and adds interactive elements to take full advantage of the web.

<iframe src="http://rstudio-pubs-static.s3.amazonaws.com/6548_bf7117f0a97f4d1987decc665e61af1b.html"></iframe>

---

## Morris.js

Morris.js is the library that powers the graphs on http://howmanyleft.co.uk/. It's a very simple API for drawing line, bar, area and donut charts.

<iframe src="http://rstudio-pubs-static.s3.amazonaws.com/6552_65410d8b706c4adaa150626bf434fc68.html"></iframe>

---

## NVD3

A reusable chart library for d3.JS.

<iframe src="http://rstudio-pubs-static.s3.amazonaws.com/6553_abc73ce032294a6080df41aa9876da67.html"></iframe>

---

## xCharts

xCharts is a D3-based library for building custom charts and graphs. Written and maintained by tenXer.

<iframe src="http://rstudio-pubs-static.s3.amazonaws.com/6554_5f8b6a7f0b834b7e96f95e793df9799b.html"></iframe>

---

## HighCharts

Highcharts is a charting library written in pure HTML5/JavaScript, offering intuitive, interactive charts to your web site or web application. Highcharts currently supports line, spline, area, areaspline, column, bar, pie, scatter, angular gauges, arearange, areasplinerange, columnrange, bubble, box plot, error bars, funnel, waterfall and polar chart types.

<iframe src="http://rstudio-pubs-static.s3.amazonaws.com/6555_32f1c0d63ba54b448af4fae94a48b70f.html"></iframe>

---

## Rickshaw

Rickshaw is a JavaScript toolkit for creating interactive time series graphs, developed at Shutterstock

<iframe src="http://rstudio-pubs-static.s3.amazonaws.com/6556_0804ff1ac33148f3ad49810a17172a59.html"></iframe>

--- 

## Confession

> * 実はこれらのライブラリの使い方は知らないです
> * ライブラリの使い方を知らなくても、使う方法があるのです
> * R の知識があればね！
> * このスライドにのせてあるサンプルも rCharts という R のパッケージで作りました

--- .segue .dark

## rCharts

---

## What is rCharts ?

* rCharts is an R package to create, customize and publish interactive javascript visualizations from R using a familiar lattice style plotting interface.
* This project is maintained by [Ramnath Vaidyanathan](https://github.com/ramnathv)

  <img src="http://secure.gravatar.com/avatar/5cf92204cc3691d9a5155632012d8644?s=200" />

---

## How to use

<iframe src="http://www.slideshare.net/slideshow/embed_code/22280400" width="597" height="486" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC;border-width:1px 1px 0;margin-bottom:5px" allowfullscreen webkitallowfullscreen mozallowfullscreen> </iframe>

---

## Sample : Morris.js

```r
data(economics, package = 'ggplot2')
econ <- transform(economics, date = as.character(date))
m1 <- mPlot(x = 'date', y = c('psavert', 'uempmed'), type = 'Line', data = econ)
m1$set(pointSize = 0, lineWidth = 1)
m1
```

<iframe src="http://rstudio-pubs-static.s3.amazonaws.com/6552_65410d8b706c4adaa150626bf434fc68.html"></iframe>

---

## Sample : NVD3

```r
hair_eye_male <- subset(as.data.frame(HairEyeColor), Sex == "Male")
n1 <- nPlot(Freq ~ Hair, group = "Eye", data = hair_eye_male, type = 'multiBarChart')
n1
```

<iframe src="http://rstudio-pubs-static.s3.amazonaws.com/6553_abc73ce032294a6080df41aa9876da67.html"></iframe>
