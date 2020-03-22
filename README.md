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
2020-03-21, we have:

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

![](README_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

Select a few countries with exponential growth in comparison with China:

![](README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

Renormalize the growth starting with the 100th confirmed case. Here is
the list of countries:

|    | Region         | Date       |
| -- | :------------- | :--------- |
| 8  | China          | 2020-01-22 |
| 9  | Cruise Ship    | 2020-02-10 |
| 26 | Korea, South   | 2020-02-20 |
| 25 | Japan          | 2020-02-21 |
| 24 | Italy          | 2020-02-23 |
| 21 | Iran           | 2020-02-26 |
| 15 | France         | 2020-02-29 |
| 40 | Singapore      | 2020-02-29 |
| 16 | Germany        | 2020-03-01 |
| 42 | Spain          | 2020-03-02 |
| 48 | US             | 2020-03-03 |
| 44 | Switzerland    | 2020-03-05 |
| 47 | United Kingdom | 2020-03-05 |
| 4  | Belgium        | 2020-03-06 |
| 29 | Netherlands    | 2020-03-06 |
| 30 | Norway         | 2020-03-06 |
| 43 | Sweden         | 2020-03-06 |
| 2  | Austria        | 2020-03-08 |
| 28 | Malaysia       | 2020-03-09 |
| 1  | Australia      | 2020-03-10 |
| 3  | Bahrain        | 2020-03-10 |
| 11 | Denmark        | 2020-03-10 |
| 6  | Canada         | 2020-03-11 |
| 23 | Israel         | 2020-03-11 |
| 36 | Qatar          | 2020-03-11 |
| 18 | Iceland        | 2020-03-12 |
| 5  | Brazil         | 2020-03-13 |
| 10 | Czechia        | 2020-03-13 |
| 14 | Finland        | 2020-03-13 |
| 17 | Greece         | 2020-03-13 |
| 35 | Portugal       | 2020-03-13 |
| 41 | Slovenia       | 2020-03-13 |
| 13 | Estonia        | 2020-03-14 |
| 19 | India          | 2020-03-14 |
| 22 | Ireland        | 2020-03-14 |
| 33 | Philippines    | 2020-03-14 |
| 34 | Poland         | 2020-03-14 |
| 37 | Romania        | 2020-03-14 |
| 39 | Saudi Arabia   | 2020-03-14 |
| 20 | Indonesia      | 2020-03-15 |
| 45 | Thailand       | 2020-03-15 |
| 7  | Chile          | 2020-03-16 |
| 31 | Pakistan       | 2020-03-16 |
| 27 | Luxembourg     | 2020-03-17 |
| 32 | Peru           | 2020-03-17 |
| 38 | Russia         | 2020-03-17 |
| 12 | Ecuador        | 2020-03-18 |
| 46 | Turkey         | 2020-03-19 |

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
    ## T1  3.36844    0.01325   254.3   <2e-16 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 726 on 18 degrees of freedom
    ## 
    ## Number of iterations to convergence: 5 
    ## Achieved convergence tolerance: 1.748e-07

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
when the `5th death` was recorded in each country:

Renormalizing the start dates for `recorded deaths`, we find the dates
when the `10th death` was recorded in each country:

|    | Country        | Start |
| -- | :------------- | ----: |
| 4  | China          |  \-23 |
| 10 | Iran           |    10 |
| 11 | Italy          |    11 |
| 13 | Korea, South   |    11 |
| 21 | US             |    19 |
| 6  | France         |    22 |
| 17 | Spain          |    22 |
| 12 | Japan          |    24 |
| 14 | Netherlands    |    28 |
| 19 | Switzerland    |    28 |
| 20 | United Kingdom |    29 |
| 7  | Germany        |    30 |
| 15 | Philippines    |    30 |
| 1  | Belgium        |    32 |
| 9  | Indonesia      |    33 |
| 18 | Sweden         |    33 |
| 2  | Brazil         |    35 |
| 3  | Canada         |    35 |
| 5  | Denmark        |    36 |
| 8  | Greece         |    36 |
| 16 | Portugal       |    36 |

![](README_files/figure-gfm/unnamed-chunk-18-1.png)<!-- -->
