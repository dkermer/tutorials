---
title: "SPSS to R"
date: 2020-04-20T21:34:54-04:00
draft: true
tags: ["One", "Two"]

---

Description 

<!--more-->

## Differences to Know

- Any comparison with a missing value is TRUE, not false. 
- Only integer values can have labels



## New Things to Know

- To add labels to values, make them a "factor". Refer to the categories with their labels, not values
- The dataset must be 



## SPSS to R

- Number of Variables and Cases -> See Environment Tab or str(), glimpse

- View Data  - Click icon or View()

- Value Labels - as_factor(), 

- Variable Information - str()

- Add/Change Variable Label

  - ```
    attr(df$x, "label") <- "This is an example variable label"
    library(labelled)
    
    var_label(iris$Sepal.Length) <- "Length of sepal"
    var_label(iris) <- list(Petal.Length = "Length of petal", Petal.Width = "Width of Petal")
    ```

- Add/Change Value Label

  - ```r
    levels(a) <- c('c', 'not-c')
    fct_??
    ```

- Add User Missing Values

  - na_if

- Rename Variable

  - rename

- Weighting

  - See something else

- Frequencies

  - dfSummary - something in tidyverse also has view
  - freq

- Descriptives

  - descr()

- Crosstabs

  - ctable()

- Choose variables

  - select

- Select Cases

  - filter

- Recode

  - fct_recode or many others

- Create Indicator Variable

  - 

- Compute

  - mutate() - for formulas
  - For mean of multiple variables? 

- Scale Reliability

  - ```r
    psych::alpha(d)
    ggplot also has alpha
    ```

- Compare Groups / Split File

  - maybe group_by in tidyverse? 

- Chi-Square

  - `data %$% ctable(chisq=TRUE)`

- T-Test

- ANOVA

- Pearson Correlation

- Regression







```
genderweight %>%
  group_by(group) %>%
  get_summary_stats(weight, type = "mean_sd")
```