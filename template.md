Homework 1
================

\#\#Problem 1 Variable types & coercion

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.4     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
    ## ✓ readr   2.0.1     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
hw_1 = tibble( 
samp = rnorm(10),
gr_0 = samp > 0,
vec_char = c("a", "b", "c", "d", "e", "f", "g", "h", "i", "j" ),
vec_level = factor(c("high", "medium", "low", "medium", "high", "low", "high", "medium", "high", "low"))
 )

hw_1
```

    ## # A tibble: 10 × 4
    ##       samp gr_0  vec_char vec_level
    ##      <dbl> <lgl> <chr>    <fct>    
    ##  1 -1.42   FALSE a        high     
    ##  2  0.357  TRUE  b        medium   
    ##  3 -0.103  FALSE c        low      
    ##  4 -0.125  FALSE d        medium   
    ##  5 -0.0136 FALSE e        high     
    ##  6  0.0976 TRUE  f        low      
    ##  7 -1.21   FALSE g        high     
    ##  8  1.18   TRUE  h        medium   
    ##  9 -0.603  FALSE i        high     
    ## 10 -0.129  FALSE j        low

``` r
mean(pull(hw_1, var = samp))
```

    ## [1] -0.1966029

``` r
mean(pull(hw_1, var = gr_0))
```

    ## [1] 0.3

``` r
mean(pull(hw_1, var = vec_char))
```

    ## Warning in mean.default(pull(hw_1, var = vec_char)): argument is not numeric or
    ## logical: returning NA

    ## [1] NA

``` r
mean(pull(hw_1, var = vec_level))
```

    ## Warning in mean.default(pull(hw_1, var = vec_level)): argument is not numeric or
    ## logical: returning NA

    ## [1] NA

I am able to take the mean of the variable “samp,” which is the random
sample size of 10 that follows a normal distribution. I am also able to
take the mean of the variable “gr\_0,” which is the summ of the
variables that are greater than 0. I am unable to take the mean for
vec\_char and vec\_level because those are not numeric, instead they are
characters.
