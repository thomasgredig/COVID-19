report-COVID-19
================
Thomas Gredig
3/12/2020

# COVID-19

We determine the order of countries it spread using the exponential
growth model and determine that it started in China, then spread to
Iran, South Korea, Italy, U.S., France, and then Spain based on
confirmed deaths.

Japan and South Korea have a much slower growth in the death rate (see
graph at the bottom). China, Italy, and U.S. appear to have common
trajectories.

The data is from the [CSSE COVID-19
Dataset](https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data)
after analysis of [Coronavirus by Tomas
Pueyo](https://medium.com/@tomaspueyo/coronavirus-act-today-or-people-will-die-f4d3d9cd99ca).

## Time Series

Regions with more than 100 confirmed cases increased rapidly from Mar 1
to Mar 11:

![](README_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

Only **some days later** the list of countries hugely expanded, so on
2020-03-15, we have:

![](README_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

Select a few countries with exponential growth in comparison with China:

![](README_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

Renormalize the growth starting with the 100th confirmed case. Here is
the list of countries:

|    | Region         | Date       |
| -- | :------------- | :--------- |
| 3  | China          | 2020-01-22 |
| 4  | Cruise Ship    | 2020-02-10 |
| 12 | Korea, South   | 2020-02-20 |
| 11 | Japan          | 2020-02-21 |
| 10 | Italy          | 2020-02-23 |
| 9  | Iran           | 2020-02-26 |
| 6  | France         | 2020-02-29 |
| 7  | Germany        | 2020-03-01 |
| 17 | Spain          | 2020-03-02 |
| 21 | US             | 2020-03-03 |
| 19 | Switzerland    | 2020-03-05 |
| 20 | United Kingdom | 2020-03-05 |
| 2  | Belgium        | 2020-03-06 |
| 14 | Netherlands    | 2020-03-06 |
| 15 | Norway         | 2020-03-06 |
| 18 | Sweden         | 2020-03-06 |
| 1  | Austria        | 2020-03-08 |
| 13 | Malaysia       | 2020-03-09 |
| 5  | Denmark        | 2020-03-10 |
| 16 | Qatar          | 2020-03-11 |
| 8  | Greece         | 2020-03-13 |

Make a graph with the trajectories from that point onwards:

![](README_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

Add an exponential fit:

![](README_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

    ## 
    ## Formula: Confirmed ~ A + B * exp(DateDaysNorm/T1)
    ## 
    ## Parameters:
    ##    Estimate Std. Error t value Pr(>|t|)    
    ## A  -114.922     52.180  -2.202   0.0522 .  
    ## B   191.507     25.811   7.420 2.26e-05 ***
    ## T1    4.074      0.178  22.880 5.74e-10 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 54.28 on 10 degrees of freedom
    ## 
    ## Number of iterations to convergence: 5 
    ## Achieved convergence tolerance: 4.787e-06

## Growth rates

Growth rates since 100th confirmed case in different countries for first
10 days.

![](README_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->![](README_files/figure-gfm/unnamed-chunk-8-2.png)<!-- -->

![](README_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

## Deaths

Graphing some countries with exponentially growing death rates at the
moment:

![](README_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

Renormalizing the start dates for `recorded deaths`, we find the dates
when the `5th death` was recorded in each country:

|    | Country        | Start |
| -- | :------------- | ----: |
| 1  | China          |  \-23 |
| 5  | Iran           |     9 |
| 8  | Korea, South   |     9 |
| 6  | Italy          |    10 |
| 2  | Cruise Ship    |    14 |
| 7  | Japan          |    16 |
| 13 | US             |    17 |
| 3  | France         |    20 |
| 10 | Spain          |    22 |
| 12 | United Kingdom |    25 |
| 4  | Germany        |    28 |
| 9  | Netherlands    |    28 |
| 11 | Switzerland    |    28 |

Renormalizing the start dates for `recorded deaths`, we find the dates
when the `15th death` was recorded in each country:

|    | Country        | Start |
| -- | :------------- | ----: |
| 1  | China          |  \-23 |
| 3  | Iran           |    11 |
| 4  | Italy          |    13 |
| 6  | Korea, South   |    15 |
| 10 | US             |    22 |
| 2  | France         |    23 |
| 8  | Spain          |    23 |
| 5  | Japan          |    27 |
| 9  | United Kingdom |    29 |
| 7  | Netherlands    |    30 |

![](README_files/figure-gfm/unnamed-chunk-14-1.png)<!-- -->
