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

Regions with more than 100 confirmed cases increased rapidly from Mar 1
to Mar 11:

![](README_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

Only **some days later** the list of countries hugely expanded, so on
2020-03-19, we have:

![](README_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

Select a few countries with exponential growth in comparison with China:

![](README_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

Renormalize the growth starting with the 100th confirmed case. Here is
the list of countries:

|    | Region         | Date       |
| -- | :------------- | :--------- |
| 6  | China          | 2020-01-22 |
| 7  | Cruise Ship    | 2020-02-10 |
| 21 | Korea, South   | 2020-02-20 |
| 20 | Japan          | 2020-02-21 |
| 19 | Italy          | 2020-02-23 |
| 16 | Iran           | 2020-02-26 |
| 11 | France         | 2020-02-29 |
| 30 | Singapore      | 2020-02-29 |
| 12 | Germany        | 2020-03-01 |
| 31 | Spain          | 2020-03-02 |
| 35 | US             | 2020-03-03 |
| 33 | Switzerland    | 2020-03-05 |
| 34 | United Kingdom | 2020-03-05 |
| 3  | Belgium        | 2020-03-06 |
| 24 | Netherlands    | 2020-03-06 |
| 25 | Norway         | 2020-03-06 |
| 32 | Sweden         | 2020-03-06 |
| 2  | Austria        | 2020-03-08 |
| 23 | Malaysia       | 2020-03-09 |
| 1  | Australia      | 2020-03-10 |
| 9  | Denmark        | 2020-03-10 |
| 5  | Canada         | 2020-03-11 |
| 18 | Israel         | 2020-03-11 |
| 29 | Qatar          | 2020-03-11 |
| 14 | Iceland        | 2020-03-12 |
| 4  | Brazil         | 2020-03-13 |
| 8  | Czechia        | 2020-03-13 |
| 10 | Finland        | 2020-03-13 |
| 13 | Greece         | 2020-03-13 |
| 28 | Portugal       | 2020-03-13 |
| 17 | Ireland        | 2020-03-14 |
| 27 | Poland         | 2020-03-14 |
| 15 | Indonesia      | 2020-03-15 |
| 26 | Pakistan       | 2020-03-16 |
| 22 | Luxembourg     | 2020-03-17 |

Make a graph with the trajectories from that point onwards:

![](README_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

Add an exponential fit:

![](README_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

    ## 
    ## Formula: Confirmed ~ A0 * exp(DateDaysNorm/T1)
    ## 
    ## Parameters:
    ##    Estimate Std. Error t value Pr(>|t|)    
    ## T1  3.44684    0.02314     149   <2e-16 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 532.8 on 16 degrees of freedom
    ## 
    ## Number of iterations to convergence: 5 
    ## Achieved convergence tolerance: 2.724e-07

Semi-log plot:

![](README_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

## Growth rates

Growth rates since 100th confirmed case in different countries for first
10 days.

![](README_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

## Deaths

Graphing some countries with exponentially growing death rates at the
moment:

![](README_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

Renormalizing the start dates for `recorded deaths`, we find the dates
when the `5th death` was recorded in each country:

|    | Country        | Start |
| -- | :------------- | ----: |
| 6  | China          |  \-23 |
| 13 | Iran           |     9 |
| 16 | Korea, South   |     9 |
| 14 | Italy          |    10 |
| 7  | Cruise Ship    |    14 |
| 15 | Japan          |    16 |
| 23 | US             |    17 |
| 9  | France         |    20 |
| 19 | Spain          |    22 |
| 22 | United Kingdom |    25 |
| 10 | Germany        |    28 |
| 17 | Netherlands    |    28 |
| 21 | Switzerland    |    28 |
| 20 | Sweden         |    31 |
| 3  | Belgium        |    32 |
| 1  | Australia      |    33 |
| 5  | Canada         |    33 |
| 12 | Indonesia      |    33 |
| 18 | Norway         |    33 |
| 2  | Austria        |    34 |
| 4  | Brazil         |    34 |
| 8  | Denmark        |    34 |
| 11 | Greece         |    34 |

Renormalizing the start dates for `recorded deaths`, we find the dates
when the `15th death` was recorded in each country:

|    | Country        | Start |
| -- | :------------- | ----: |
| 2  | China          |  \-23 |
| 6  | Iran           |    11 |
| 7  | Italy          |    13 |
| 9  | Korea, South   |    15 |
| 14 | US             |    22 |
| 3  | France         |    23 |
| 11 | Spain          |    23 |
| 8  | Japan          |    27 |
| 13 | United Kingdom |    29 |
| 10 | Netherlands    |    30 |
| 4  | Germany        |    31 |
| 12 | Switzerland    |    32 |
| 5  | Indonesia      |    33 |
| 1  | Belgium        |    34 |

![](README_files/figure-gfm/unnamed-chunk-14-1.png)<!-- -->
