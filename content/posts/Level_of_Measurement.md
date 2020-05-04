---
title: "Level of Measurement"
date: 2020-04-20T21:34:54-04:00
draft: true
tags: ["One", "Two"]
---

Measure Type or Measurment Level . Even though it seems weird to "measure" a person's eye color, the whole process of collecting accurate data is referred to as Measurement. The type or level matters because calculations depend on the mathematical properties of the varables. 

<!--more-->

## Qualitative

​	About a thing's Qualities.  

### Categorical & Grouping

Both these words are often used to describe these types of values. In part, this is beacuse the word Qualitative is also used to describe unstructured textual data that is not specifying categories. 

### Nominal

Nominal refers to categorical variables that do not have any natural order ("**Nom**inal" = "**Nom** de Plume" = "Pen **n**ame"). Even if you code each category with a number (becuase numbers take less processing power), the numbers have no specific meaning. They are simply a "code" representing the group. 

### Ordinal

These are categorical variables that have a natural order ("**Ord**inal" = "**Ord**er"'). Although each category has a specific non-numeric meaning, software will assign numbers to the categories in order to maintin the proper ordering. 

## Quantitative

A Quantity -- "How many?" "How much?"

### Interval & Ratio

Ratio variables are so named because ratios are meaningful. It is so because since the value 0 means none. Thus, in a Ratio variable, it is meaningful that 10 is twice 5 and 4 is twice 2. With an Interval variable, the value 0 does not mean none, so one would never say thing like "10 is twice of 5". 

Interval variables are more easily thought of as Quantitive variables without a true zero. But, they got their name 

For most statistical analysis, it is irrelevant whether a variable is interval or ratio. However, it can matter for many relevant decisions, such as data preparation and graphing.  For instance, the graphing axis for a Ratio variable should typically start at 0. For an interval variable this is not relevant. 

### Discrete & Continuous

Discrete refers to variables in which only specific values are allowed, typically meaning just whole numbers. Continuous variables, on the other hand, can theoretically take on any decimal value (within a given range, if needed). This is relevant for determining probabilities since discrete values would use a binomial distribution. However, in practice (due to the law of large numbers) there is no difference in what a researcher does. 

Some people use the word Continuous to refer to all types of quantitative variables, since even with truly continuous variables, rounding produces ultimately similar variables. 

### Scale & Numeric

Both these words are often used to refer to any quantitative variable (both Interval and Ratio). The statistical software SPSS, for example, uses the the word Scale. But, both words have additional meanings that can lead to confusion. Interval or Ratio can be answers to the question of what "scale" a variable is measured on. Numeric implies that any time numbers are used it is Quantiative. However, numbers are often used as codes (shorthand) for Qualitative variables, or have intrinsic cateagorical meaings, such as zip codes representing places. 

### Counts

Although coutns are a type of Discrete Scale variable, they merit a mention because their distribution is typically non-normal. 

## Both

### Approximately Interval

Although not an official level of measurement, many ordinal variables are thought to share the same mathamatical properties as interval variables and therefore treated as such. The most common example is Likert-type questions with response choices "Strongly Agree", "Agree", "Neutral", "Disagree", and "Storongly Disagree".  Although one cannot say for certain that the mental difference between "Strongly Agree" and "Agree" is the same as that between "Agree" and "Neutral", it is likely at least approximately so. Thus, researchers will treat such variables as either Quantitative or Qualitative, or both. 

### Dichotomous & Binary

Dichotomous is the label for a variable that has just two values. When those two values are 0 and 1, it is called Binary. 

For some statistical analyses, it is relevant whether the "underlying distribution" of the dichotomous variable is continuous or discrete. For instance, we could classify people as "liberal" or "conservative", but there is a whole continuum of ideologies between the two, and the cutoff between our two groups is likely to be arbitrary. However, voting for the Democratic or the Republican candidate has no equivalent "middle ground" no matter how difficult the decision may have been. If there is not a continuous underlying distributon, then it can be problematic to treat such a variable as continuuous (ex. correlation analysis)