report-COVID-19
================
Thomas Gredig
5/8/2020

# COVID-19

We are comparing the growth rates in different regions. Using a 1-fit
exponential model, the confirmed cases generally fit the model well. The
doubling time is then compared.

The data is from the [CSSE COVID-19
Dataset](https://github.com/CSSEGISandData/COVID-19) after analysis of
[Coronavirus by Tomas
Pueyo](https://medium.com/@tomaspueyo/coronavirus-act-today-or-people-will-die-f4d3d9cd99ca).

Projections based on [SIR
models](https://www.maa.org/press/periodicals/loci/joma/the-sir-model-for-spread-of-disease-the-differential-equation-model)
from [HealthData](https://covid19.healthdata.org/projections).

## Time Series

Regions with more than 5,000 confirmed cases increased rapidly from a
few to many.

On 2020-07-05, we have:

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

![](README_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

Select a few countries with exponential growth in comparison with China:

![](README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

Renormalize the growth starting with the 1000th confirmed case. Here is
the list of countries:

Make a graph with the trajectories from that point onwards:

![](README_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

Scale by population of the country:

![](README_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

![](README_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

## Growth rates

Growth rates since 100th confirmed case in different countries for the
first 15 days compared with the range from 15-30 days. If the dark line
is on the right, then the doubling time is decreasing; if the dark line
is left, it means that doubling time is getting faster.

![](README_files/figure-gfm/unnamed-chunk-10-1.png)<!-- -->

## Deaths

Graphing some countries with exponentially growing death rates at the
moment:

![](README_files/figure-gfm/unnamed-chunk-12-1.png)<!-- -->

Renormalizing the start dates for `recorded deaths`, we find the dates
when the `100th death` was recorded in each country:

![](README_files/figure-gfm/unnamed-chunk-15-1.png)<!-- -->

Renormalize by population:

![](README_files/figure-gfm/unnamed-chunk-16-1.png)<!-- -->

![](README_files/figure-gfm/unnamed-chunk-17-1.png)<!-- -->
