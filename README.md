report-COVID-19
================
Thomas Gredig
3/17/2020

# COVID-19

We are comparing the growth rates in different regions. Using a 1-fit
exponential model, the confirmed cases generally fit the model well. The
doubling time is then compared.

The data is from the [CSSE COVID-19
Dataset](https://github.com/CSSEGISandData/COVID-19) after analysis of
[Coronavirus by Tomas
Pueyo](https://medium.com/@tomaspueyo/coronavirus-act-today-or-people-will-die-f4d3d9cd99ca).

## Time Series

Regions with more than 100 confirmed cases increased rapidly from a few
to many.

Only **some days later** the list of countries hugely expanded, so on
2020-03-25, we have:

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

![](README_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

Select a few countries with exponential growth in comparison with China:

![](README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

Renormalize the growth starting with the 100th confirmed case. Here is
the list of countries:

|    | Region               | Date       |
| -- | :------------------- | :--------- |
| 10 | China                | 2020-01-22 |
| 15 | Diamond Princess     | 2020-02-10 |
| 33 | Korea, South         | 2020-02-20 |
| 32 | Japan                | 2020-02-21 |
| 31 | Italy                | 2020-02-23 |
| 27 | Iran                 | 2020-02-26 |
| 21 | France               | 2020-02-29 |
| 51 | Singapore            | 2020-02-29 |
| 22 | Germany              | 2020-03-01 |
| 54 | Spain                | 2020-03-02 |
| 61 | US                   | 2020-03-03 |
| 56 | Switzerland          | 2020-03-05 |
| 60 | United Kingdom       | 2020-03-05 |
| 6  | Belgium              | 2020-03-06 |
| 38 | Netherlands          | 2020-03-06 |
| 39 | Norway               | 2020-03-06 |
| 55 | Sweden               | 2020-03-06 |
| 4  | Austria              | 2020-03-08 |
| 36 | Malaysia             | 2020-03-09 |
| 3  | Australia            | 2020-03-10 |
| 5  | Bahrain              | 2020-03-10 |
| 14 | Denmark              | 2020-03-10 |
| 8  | Canada               | 2020-03-11 |
| 46 | Qatar                | 2020-03-11 |
| 24 | Iceland              | 2020-03-12 |
| 30 | Israel               | 2020-03-12 |
| 7  | Brazil               | 2020-03-13 |
| 13 | Czechia              | 2020-03-13 |
| 20 | Finland              | 2020-03-13 |
| 23 | Greece               | 2020-03-13 |
| 28 | Iraq                 | 2020-03-13 |
| 45 | Portugal             | 2020-03-13 |
| 52 | Slovenia             | 2020-03-13 |
| 18 | Egypt                | 2020-03-14 |
| 19 | Estonia              | 2020-03-14 |
| 25 | India                | 2020-03-14 |
| 29 | Ireland              | 2020-03-14 |
| 43 | Philippines          | 2020-03-14 |
| 44 | Poland               | 2020-03-14 |
| 47 | Romania              | 2020-03-14 |
| 49 | Saudi Arabia         | 2020-03-14 |
| 26 | Indonesia            | 2020-03-15 |
| 34 | Lebanon              | 2020-03-15 |
| 57 | Thailand             | 2020-03-15 |
| 9  | Chile                | 2020-03-16 |
| 40 | Pakistan             | 2020-03-16 |
| 35 | Luxembourg           | 2020-03-17 |
| 42 | Peru                 | 2020-03-17 |
| 48 | Russia               | 2020-03-17 |
| 17 | Ecuador              | 2020-03-18 |
| 53 | South Africa         | 2020-03-18 |
| 59 | United Arab Emirates | 2020-03-18 |
| 11 | Colombia             | 2020-03-19 |
| 12 | Croatia              | 2020-03-19 |
| 37 | Mexico               | 2020-03-19 |
| 41 | Panama               | 2020-03-19 |
| 50 | Serbia               | 2020-03-19 |
| 58 | Turkey               | 2020-03-19 |
| 2  | Argentina            | 2020-03-20 |
| 1  | Algeria              | 2020-03-21 |
| 16 | Dominican Republic   | 2020-03-21 |

Make a graph with the trajectories from that point onwards:

![](README_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

Scale by population of the country:

![](README_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

![](README_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

Add an exponential fit:

![](README_files/figure-gfm/unnamed-chunk-10-1.png)<!-- -->

    ## 
    ## Formula: Confirmed ~ A0 * exp(DateDaysNorm/T1)
    ## 
    ## Parameters:
    ##    Estimate Std. Error t value Pr(>|t|)    
    ## T1  3.43789    0.01014   339.1   <2e-16 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 1907 on 22 degrees of freedom
    ## 
    ## Number of iterations to convergence: 5 
    ## Achieved convergence tolerance: 3.488e-07

Semi-log plot:

![](README_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

## Growth rates

Growth rates since 100th confirmed case in different countries for the
first 10 days compared with the range from 10-20 days. If the dark line
is on the right, then the doubling time is decreasing; if the dark line
is left, it means that doubling time is getting faster.

![](README_files/figure-gfm/unnamed-chunk-12-1.png)<!-- -->

## Deaths

Graphing some countries with exponentially growing death rates at the
moment:

![](README_files/figure-gfm/unnamed-chunk-14-1.png)<!-- -->

Renormalizing the start dates for `recorded deaths`, we find the dates
when the `10th death` was recorded in each country:

|    | Country            | Start |
| -- | :----------------- | ----: |
| 6  | China              |  \-23 |
| 17 | Iran               |    10 |
| 19 | Italy              |    11 |
| 21 | Korea, South       |    11 |
| 34 | US                 |    19 |
| 12 | France             |    22 |
| 29 | Spain              |    22 |
| 20 | Japan              |    24 |
| 23 | Netherlands        |    28 |
| 31 | Switzerland        |    28 |
| 18 | Iraq               |    29 |
| 33 | United Kingdom     |    29 |
| 13 | Germany            |    30 |
| 25 | Philippines        |    30 |
| 3  | Belgium            |    32 |
| 16 | Indonesia          |    33 |
| 30 | Sweden             |    33 |
| 1  | Algeria            |    35 |
| 4  | Brazil             |    35 |
| 5  | Canada             |    35 |
| 7  | Denmark            |    36 |
| 11 | Egypt              |    36 |
| 14 | Greece             |    36 |
| 27 | Portugal           |    36 |
| 2  | Austria            |    37 |
| 10 | Ecuador            |    37 |
| 22 | Malaysia           |    37 |
| 32 | Turkey             |    37 |
| 15 | India              |    38 |
| 24 | Norway             |    38 |
| 8  | Diamond Princess   |    39 |
| 26 | Poland             |    39 |
| 28 | Romania            |    39 |
| 9  | Dominican Republic |    40 |

![](README_files/figure-gfm/unnamed-chunk-17-1.png)<!-- -->

Trying to add a fit line:

![](README_files/figure-gfm/unnamed-chunk-18-1.png)<!-- -->

Renormalize by population:

![](README_files/figure-gfm/unnamed-chunk-19-1.png)<!-- -->
