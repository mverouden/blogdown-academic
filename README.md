Blogdown Academic site
================

<!-- README.md is generated from README.Rmd. Please edit that file -->

## Versions

- Wowchemy starter-hugo-academic theme v5.5.0
- Hugo extended v0.111.3 via install_hugo(version = “0.111.3”, extended
  = TRUE) with a softlink to /usr/local/bin/hugo (see
  <https://github.com/gohugoio/hugo/releases>)
- GO version 1.20.2 (see <https://go.dev/doc/install>) modified
  /etc/profile

``` sh
# set PATH so it includes /usr/local/go/bin if it exists
if [ -d "/usr/local/go/bin" ] ; then
    PATH="/usr/local/go/bin:$PATH"
fi
```

## GitHub Documents

This is an R Markdown format used for publishing markdown documents to
GitHub. When you click the **Knit** button all R code chunks are run and
a markdown file (.md) suitable for publishing to GitHub is generated.

Here’s our logo (hover to see the title text):

Inline-style:  
![alt text](https://db.yihui.name/images/hex-blogdown.png)

Reference-style:  
![alt text1](http://hexb.in/hexagons/rmarkdown.png)

## Including Code

You can include R code in the document as follows:

``` r
summary(cars)
```

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

## Including Plots

You can also embed plots, for example:

![](README_files/figure-gfm/pressure-1.png)<!-- -->

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
