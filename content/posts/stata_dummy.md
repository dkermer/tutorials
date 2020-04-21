---
title: "Stata Dummy Coding"
date: 2020-04-21T12:52:41-04:00
draft: false
---

The rule is that you have to use i. or c. when you want to change the 
default way that the variables are handled. Note also that stata uses 
the term "Factor" to mean a categorical variable (other software does 
this too).

For instance, Stata assumes the IV's of an ANOVA are categorical. So, if 
you wanted to include continuous covariates, you would have to put 
c.var. Stata asusmes the IV's of a Regression are continuous, which is 
why you typically have to put i.var.

However, when you create an interaction, it assumes that the variables 
used for an interaction are categorical (since most interactions are 
done with categorical variables and that is far easier to interpret). 
Thus, if you want to have an interaction with continuous variables, you 
have to again specify the c.var. It doesn't hurt to put extra i.'s and 
c.'s to clarify the interpretation, which is what they seem to do.

Note that for binary variables (0/1), it does not matter whether you put 
i. or not. Both ways will be treated the same mathematically, but the 
output will look slightly different.