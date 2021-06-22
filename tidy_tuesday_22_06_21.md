---
title: "tidy_tuesday_22_06_21"
author: "Laith Alayassa"
date: "6/22/2021"
output: 
  html_document:
    keep_md: TRUE
    toc: TRUE
    toc_float: TRUE
    df_print: paged
    code_download: true
---




```r
library(tidyverse)     # for graphing and data cleaning
```

```
## -- Attaching packages --------------------------------------- tidyverse 1.3.1 --
```

```
## v ggplot2 3.3.3     v purrr   0.3.4
## v tibble  3.1.2     v dplyr   1.0.6
## v tidyr   1.1.3     v stringr 1.4.0
## v readr   1.4.0     v forcats 0.5.1
```

```
## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
## x dplyr::filter() masks stats::filter()
## x dplyr::lag()    masks stats::lag()
```

```r
library(lubridate)     # for date manipulation
```

```
## 
## Attaching package: 'lubridate'
```

```
## The following objects are masked from 'package:base':
## 
##     date, intersect, setdiff, union
```

```r
library(ggthemes)      # for even more plotting themes
theme_set(theme_minimal()) # My favorite ggplot() theme :)
```


```r
# Get the Data

# Read in with tidytuesdayR package 
# Install from CRAN via: install.packages("tidytuesdayR")
# This loads the readme and all the datasets for the week of interest

# Either ISO-8601 date or year/week works!

tuesdata <- tidytuesdayR::tt_load('2021-06-22')
```

```
## --- Compiling #TidyTuesday Information for 2021-06-22 ----
```

```
## --- There is 1 file available ---
```

```
## --- Starting Download ---
```

```
## 
## 	Downloading file 1 of 1: `parks.csv`
```

```
## --- Download complete ---
```

```r
tuesdata <- tidytuesdayR::tt_load(2021, week = 26)
```

```
## --- Compiling #TidyTuesday Information for 2021-06-22 ----
```

```
## --- There is 1 file available ---
```

```
## --- Starting Download ---
```

```
## 
## 	Downloading file 1 of 1: `parks.csv`
```

```
## --- Download complete ---
```

```r
parks <- tuesdata$parks

# Or read in the data manually

parks <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2021/2021-06-22/parks.csv')
```

```
## 
## -- Column specification --------------------------------------------------------
## cols(
##   .default = col_double(),
##   city = col_character(),
##   park_pct_city_data = col_character(),
##   pct_near_park_data = col_character(),
##   spend_per_resident_data = col_character(),
##   city_dup = col_character()
## )
## i Use `spec()` for the full column specifications.
```

