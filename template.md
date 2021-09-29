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

### Loading Penguins to the Dataset

``` r_problem2
library(tidyverse)

data("penguins", package = "palmerpenguins")

nrow(penguins)
ncol(penguins)

mean(pull(penguins, var = flipper_length_mm), na.rm = TRUE)
```

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

### GGPlot
