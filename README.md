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
2020-03-23, we have:

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

![](README_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

Select a few countries with exponential growth in comparison with China:

![](README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

Renormalize the growth starting with the 100th confirmed case. Here is
the list of countries:

|    | Region         | Date       |
| -- | :------------- | :--------- |
| 9  | China          | 2020-01-22 |
| 11 | Cruise Ship    | 2020-02-10 |
| 29 | Korea, South   | 2020-02-20 |
| 28 | Japan          | 2020-02-21 |
| 27 | Italy          | 2020-02-23 |
| 24 | Iran           | 2020-02-26 |
| 18 | France         | 2020-02-29 |
| 45 | Singapore      | 2020-02-29 |
| 19 | Germany        | 2020-03-01 |
| 48 | Spain          | 2020-03-02 |
| 54 | US             | 2020-03-03 |
| 50 | Switzerland    | 2020-03-05 |
| 53 | United Kingdom | 2020-03-05 |
| 5  | Belgium        | 2020-03-06 |
| 33 | Netherlands    | 2020-03-06 |
| 34 | Norway         | 2020-03-06 |
| 49 | Sweden         | 2020-03-06 |
| 3  | Austria        | 2020-03-08 |
| 31 | Malaysia       | 2020-03-09 |
| 2  | Australia      | 2020-03-10 |
| 4  | Bahrain        | 2020-03-10 |
| 13 | Denmark        | 2020-03-10 |
| 7  | Canada         | 2020-03-11 |
| 26 | Israel         | 2020-03-11 |
| 41 | Qatar          | 2020-03-11 |
| 21 | Iceland        | 2020-03-12 |
| 6  | Brazil         | 2020-03-13 |
| 12 | Czechia        | 2020-03-13 |
| 17 | Finland        | 2020-03-13 |
| 20 | Greece         | 2020-03-13 |
| 40 | Portugal       | 2020-03-13 |
| 46 | Slovenia       | 2020-03-13 |
| 15 | Egypt          | 2020-03-14 |
| 16 | Estonia        | 2020-03-14 |
| 22 | India          | 2020-03-14 |
| 25 | Ireland        | 2020-03-14 |
| 38 | Philippines    | 2020-03-14 |
| 39 | Poland         | 2020-03-14 |
| 42 | Romania        | 2020-03-14 |
| 44 | Saudi Arabia   | 2020-03-14 |
| 23 | Indonesia      | 2020-03-15 |
| 51 | Thailand       | 2020-03-15 |
| 8  | Chile          | 2020-03-16 |
| 35 | Pakistan       | 2020-03-16 |
| 30 | Luxembourg     | 2020-03-17 |
| 37 | Peru           | 2020-03-17 |
| 43 | Russia         | 2020-03-17 |
| 14 | Ecuador        | 2020-03-18 |
| 47 | South Africa   | 2020-03-18 |
| 10 | Croatia        | 2020-03-19 |
| 32 | Mexico         | 2020-03-19 |
| 36 | Panama         | 2020-03-19 |
| 52 | Turkey         | 2020-03-19 |
| 1  | Argentina      | 2020-03-20 |

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
    ## T1 3.373862   0.006416   525.8   <2e-16 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 703.3 on 20 degrees of freedom
    ## 
    ## Number of iterations to convergence: 5 
    ## Achieved convergence tolerance: 1.522e-08

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
| 5  | China          |  \-23 |
| 14 | Iran           |    10 |
| 15 | Italy          |    11 |
| 17 | Korea, South   |    11 |
| 28 | US             |    19 |
| 9  | France         |    22 |
| 23 | Spain          |    22 |
| 16 | Japan          |    24 |
| 19 | Netherlands    |    28 |
| 25 | Switzerland    |    28 |
| 27 | United Kingdom |    29 |
| 10 | Germany        |    30 |
| 21 | Philippines    |    30 |
| 2  | Belgium        |    32 |
| 13 | Indonesia      |    33 |
| 24 | Sweden         |    33 |
| 3  | Brazil         |    35 |
| 4  | Canada         |    35 |
| 6  | Denmark        |    36 |
| 8  | Egypt          |    36 |
| 11 | Greece         |    36 |
| 22 | Portugal       |    36 |
| 1  | Austria        |    37 |
| 7  | Ecuador        |    37 |
| 18 | Malaysia       |    37 |
| 26 | Turkey         |    37 |
| 12 | India          |    38 |
| 20 | Norway         |    38 |

![](README_files/figure-gfm/unnamed-chunk-18-1.png)<!-- -->

Trying to add a fit line:

![](README_files/figure-gfm/unnamed-chunk-19-1.png)<!-- -->
