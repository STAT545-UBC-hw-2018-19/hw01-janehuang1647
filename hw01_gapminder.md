Requirement of the Assignment
-----------------------------

Make an R Markdown document that explores a dataset, such as gapminder
seen in class. You don't need an extensive exploration in order to get a
good grade here; a basic one will do, not unlike the one done in class,
which would be considered sufficient (but less so the more verbatim your
submission is). Render your R Markdown to the github\_document output
format. Commit both the .Rmd and .md files and push them to GitHub.

load the Gapminder database
===========================

    library(gapminder)

structure of the object
=======================

    str(gapminder)

    ## Classes 'tbl_df', 'tbl' and 'data.frame':    1704 obs. of  6 variables:
    ##  $ country  : Factor w/ 142 levels "Afghanistan",..: 1 1 1 1 1 1 1 1 1 1 ...
    ##  $ continent: Factor w/ 5 levels "Africa","Americas",..: 3 3 3 3 3 3 3 3 3 3 ...
    ##  $ year     : int  1952 1957 1962 1967 1972 1977 1982 1987 1992 1997 ...
    ##  $ lifeExp  : num  28.8 30.3 32 34 36.1 ...
    ##  $ pop      : int  8425333 9240934 10267083 11537966 13079460 14880372 12881816 13867957 16317921 22227415 ...
    ##  $ gdpPercap: num  779 821 853 836 740 ...

explore the database with different functions
=============================================

    class(gapminder)

    ## [1] "tbl_df"     "tbl"        "data.frame"

    head(gapminder) ## return the first part of the database

    ## # A tibble: 6 x 6
    ##   country     continent  year lifeExp      pop gdpPercap
    ##   <fct>       <fct>     <int>   <dbl>    <int>     <dbl>
    ## 1 Afghanistan Asia       1952    28.8  8425333      779.
    ## 2 Afghanistan Asia       1957    30.3  9240934      821.
    ## 3 Afghanistan Asia       1962    32.0 10267083      853.
    ## 4 Afghanistan Asia       1967    34.0 11537966      836.
    ## 5 Afghanistan Asia       1972    36.1 13079460      740.
    ## 6 Afghanistan Asia       1977    38.4 14880372      786.

    tail(gapminder) ## return the lsat part of the database

    ## # A tibble: 6 x 6
    ##   country  continent  year lifeExp      pop gdpPercap
    ##   <fct>    <fct>     <int>   <dbl>    <int>     <dbl>
    ## 1 Zimbabwe Africa     1982    60.4  7636524      789.
    ## 2 Zimbabwe Africa     1987    62.4  9216418      706.
    ## 3 Zimbabwe Africa     1992    60.4 10704340      693.
    ## 4 Zimbabwe Africa     1997    46.8 11404948      792.
    ## 5 Zimbabwe Africa     2002    40.0 11926563      672.
    ## 6 Zimbabwe Africa     2007    43.5 12311143      470.

    names(gapminder)  ## get the name of the object

    ## [1] "country"   "continent" "year"      "lifeExp"   "pop"       "gdpPercap"

    length(gapminder) ## get the length of the factor

    ## [1] 6

    nrow(gapminder) ## number of rows in the database

    ## [1] 1704

    summary(gapminder) ## statistical overview

    ##         country        continent        year         lifeExp     
    ##  Afghanistan:  12   Africa  :624   Min.   :1952   Min.   :23.60  
    ##  Albania    :  12   Americas:300   1st Qu.:1966   1st Qu.:48.20  
    ##  Algeria    :  12   Asia    :396   Median :1980   Median :60.71  
    ##  Angola     :  12   Europe  :360   Mean   :1980   Mean   :59.47  
    ##  Argentina  :  12   Oceania : 24   3rd Qu.:1993   3rd Qu.:70.85  
    ##  Australia  :  12                  Max.   :2007   Max.   :82.60  
    ##  (Other)    :1632                                                
    ##       pop              gdpPercap       
    ##  Min.   :6.001e+04   Min.   :   241.2  
    ##  1st Qu.:2.794e+06   1st Qu.:  1202.1  
    ##  Median :7.024e+06   Median :  3531.8  
    ##  Mean   :2.960e+07   Mean   :  7215.3  
    ##  3rd Qu.:1.959e+07   3rd Qu.:  9325.5  
    ##  Max.   :1.319e+09   Max.   :113523.1  
    ## 

Extract data from the database for analysis
===========================================

    mean(gapminder$lifeExp) ## mean of the lifeExp

    ## [1] 59.47444

    median(gapminder$year) ## median of the year

    ## [1] 1979.5

    var(gapminder$pop) ## variance of population

    ## [1] 1.12695e+16

visualising the data
====================

    plot(lifeExp ~ year, gapminder)  ## plot the graph of lifeExp against the year

![](hw01_gapminder_files/figure-markdown_strict/unnamed-chunk-5-1.png)
