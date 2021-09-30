Homework 1
================

# Problem 1

Variable types & coercion

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
    ##  1 -0.400  FALSE a        high     
    ##  2 -0.466  FALSE b        medium   
    ##  3 -0.0572 FALSE c        low      
    ##  4  1.76   TRUE  d        medium   
    ##  5 -2.13   FALSE e        high     
    ##  6 -0.154  FALSE f        low      
    ##  7 -0.568  FALSE g        high     
    ##  8  1.26   TRUE  h        medium   
    ##  9  0.193  TRUE  i        high     
    ## 10 -0.771  FALSE j        low

``` r
mean(pull(hw_1, var = samp))
```

    ## [1] -0.1327465

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

``` r
as.numeric(pull(hw_1, gr_0))
as.numeric(pull(hw_1,vec_char))
as.numeric(pull(hw_1, vec_level))
```

The logic and factor variables are able to convert to numeric variables,
presumably because they are ordered (true/false, and 3 levels). The
character variable is not able to convert to numberic because it is not
an ordered variable. After this conversion, I would be able to calculate
the mean of the factor variable but still not the character.

# Problem 2

### Loading Penguins to the Dataset

``` r
library(tidyverse)

data("penguins", package="palmerpenguins")
```

The penguin data set has the following variables; species, island,
bill\_length\_mm, bill\_depth\_mm, flipper\_length\_mm, body\_mass\_g,
sex, year. It has 8 columns and 344 rows. The mean flipper length is
200.9152047

-   Penguins Data set

    -   The data set has 8 variables
        -   species (character)
        -   island (character)
        -   bill length in mm (numerical)  
        -   bill depth in mm (numerical)
        -   flipper length in mm (numerical)
        -   body mass in g (numerical)
        -   sex (character)
        -   year (numerical)
    -   There are 344 rows and 8 columns
    -   the mean flipper length is 200.9152 mm

## Problem 2

#### GGPlot

``` r
library(ggplot2)

penguin_ggplot = ggplot(data = penguins, aes (x = bill_length_mm, y = flipper_length_mm, color = species)) + geom_point()

ggsave("penguin_ggplot.jpg", plot = penguin_ggplot)
```

    ## Saving 7 x 5 in image

``` r
penguin_ggplot
```

![](template_files/figure-gfm/ggplot-1.png)<!-- -->

Plot of penguin bill length compared to flipper length is shown here:
