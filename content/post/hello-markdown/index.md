---
authors:
- admin
categories: ["R"]
date: "2015-07-23T21:13:14-07:00"
draft: true
featured: false
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/cfDrdaslu7o)'
  focal_point: ""
  preview_only: false
projects: []
subtitle: "Create a simple Markdown post with R code in under 10 minutes :smile:"
summary: Creating simple markdown posts
tags: ["R Markdown", "plot", "regression"]
title: "Hello Markdown with R"
---

# R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

You can embed an R code chunk like this:


```r
summary(cars)
##      speed           dist       
##  Min.   : 4.0   Min.   :  2.00  
##  1st Qu.:12.0   1st Qu.: 26.00  
##  Median :15.0   Median : 36.00  
##  Mean   :15.4   Mean   : 42.98  
##  3rd Qu.:19.0   3rd Qu.: 56.00  
##  Max.   :25.0   Max.   :120.00
fit <- lm(dist ~ speed, data = cars)
fit
## 
## Call:
## lm(formula = dist ~ speed, data = cars)
## 
## Coefficients:
## (Intercept)        speed  
##     -17.579        3.932
```

# Including Plots

You can also embed plots. See Figure <a href="#fig:pie">1</a> for example:


```r
par(mar = c(0, 1, 0, 1))
pie(
  c(280, 60, 20),
  c('Sky', 'Sunny side of pyramid', 'Shady side of pyramid'),
  col = c('#0292D8', '#F7EA39', '#C4B632'),
  init.angle = -50, border = NA
)
```

<div class="figure">
<img src="/post/hello-markdown/index_files/figure-html/pie-1.png" alt="A fancy pie chart." width="672" />
<p class="caption">Figure 1: A fancy pie chart.</p>
</div>

# I :heart: Academic :smile:
