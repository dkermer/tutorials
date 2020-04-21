---
title: "Regression"
date: 2020-04-21T13:18:15-04:00
draft: true
---

Regression is a way of finding a mathematical equation that best predicts or estimates a value (called “Y”) from one or more other values (each called “X”). For instance, we might want to be able to predict or estimate a person's XXX when we know their YYY and YYY. 

Other words for "Y" include *Outcome* and *Dependent Variable*. 

Other words for X include *Predictors* and *Independent Variables*. 

<!--more-->

The computer can create this equation from a dataset with many examples of X values and their related Y value.  If any of the values are missing, the computer cannot use that case (or row) to help make the equation. 

The equation, at it's most basic, is just multiplying and adding. 

-   If the relationship is strong, differences in what we know of the value
    of an X would lead us to make big changes in our prediction of the Y. Thus the multiplier for that X is large. 
-   If the relationship is weak, we wouldn’t change our prediction of the Y
    based on knowing the X. Thus the multiplier for that X is small. 
-   If the coefficient is 0, then we don’t change our prediction of Y at all (since
    0 x anything = 0).
-   We call each multiplier a “coefficient”. 

The computer then figures out the values that make the difference between it's calculation for the Y value and the actual Y value is the smallest. 