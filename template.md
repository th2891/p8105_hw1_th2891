Homework 1
================

# Problem 1

Variable types & coercion

``` r_hw1part1
library(tidyverse)

hw_1 = tibble( 
samp = rnorm(10),
gr_0 = samp > 0,
vec_char = c("a", "b", "c", "d", "e", "f", "g", "h", "i", "j" ),
vec_level = factor(c("high", "medium", "low", "medium", "high", "low", "high", "medium", "high", "low"))
 )

hw_1

mean(pull(hw_1, var = samp))
mean(pull(hw_1, var = gr_0))
mean(pull(hw_1, var = vec_char))
mean(pull(hw_1, var = vec_level))
```

I am able to take the mean of the variable “samp,” which is the random
sample size of 10 that follows a normal distribution. I am also able to
take the mean of the variable “gr\_0,” which is the summ of the
variables that are greater than 0. I am unable to take the mean for
vec\_char and vec\_level because those are not numeric, instead they are
characters.

``` r_hw1part2
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

### loading Penguins to the dataset

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
data("penguins", package = "palmerpenguins")

penguins
```

    ## # A tibble: 344 × 8
    ##    species island    bill_length_mm bill_depth_mm flipper_length_mm body_mass_g
    ##    <fct>   <fct>              <dbl>         <dbl>             <int>       <int>
    ##  1 Adelie  Torgersen           39.1          18.7               181        3750
    ##  2 Adelie  Torgersen           39.5          17.4               186        3800
    ##  3 Adelie  Torgersen           40.3          18                 195        3250
    ##  4 Adelie  Torgersen           NA            NA                  NA          NA
    ##  5 Adelie  Torgersen           36.7          19.3               193        3450
    ##  6 Adelie  Torgersen           39.3          20.6               190        3650
    ##  7 Adelie  Torgersen           38.9          17.8               181        3625
    ##  8 Adelie  Torgersen           39.2          19.6               195        4675
    ##  9 Adelie  Torgersen           34.1          18.1               193        3475
    ## 10 Adelie  Torgersen           42            20.2               190        4250
    ## # … with 334 more rows, and 2 more variables: sex <fct>, year <int>

``` r
mean(pull(penguins, var = flipper_length_mm))
```

    ## [1] NA

-   Penguins Data set

    -   Variables include; species, island, bill length (mm), bill depth
        (mm) flipper length (mm). body mass (g), sex, and year
    -   344 x 8 table
