---
title: "Null Hypothesis Significance Testing"
date: 2020-04-21T13:48:12-04:00
draft: true
---

Part 1: The Hypotheses
----------------------

The "Null Hypothesis" part of significance testing is relevant. If there is no null hyptohesis, then the rules are completely different. 

**Null Hypothesis H0**

​	examples:  μ = 10    μ ≤ 10    μ ≥ 10   (equal signs)

-   The status quo

-   "No true difference" *or* "No true relationship"

-   Any relationship or difference in the sample due to chance

**Alternative Hypothesis Ha **

​	examples: μ ≠ 10   μ \> 10   μ \< 10		(no equal signs)

-   What you really think and want to convince others of

-   What you can get published

-   "There is a difference" *or* "There is a relationship"



## Part 2: The Test

Which test will depend on the hypothesis (difference vs relationship), data
(independent vs paired), how many variables are involved, and their level of
measurement (categorical vs quantitative), Tests that compare two groups can be one 1 or 2-tailed, depending on whether you want to test if a particular group mean is larger, or just whether there is a difference.

Each statistical test produces a different **test statistic**, which is represented by a letter or greek symbol. 

c. Identify the test-statistic you will get

d. Historically: look up the critical value

Part 3: The Data
----------------

a. Calculate Summary/Descriptive Statistics or create charts or graphs to
examine your data for the difference or relationship you hypothesized. If you do
not see an effect that is substantial , it does not matter what the p-value is.

d. Perform Calculations on the Data you Have

1. Historically: Test Statistic. In many tests this can be done by hand (or with
   a calculator). But, computers do this for us.. Each test statistic has it's own distribution. By itself, it has no meaning, except that the larger it is (or farther from zero) the lower the p-value will be.

2. Modern: P-Value / probability value. This is difficult to compute by hand, so
   historically it wasn't calculated. But, with computers, we can get an exact
   p-value for our specific data. A p-value puts the value of the test statistic on a common and interpretable scale.
   - When p-values are less than .001, they are just reported as "**p < .001**". These also should be reported as p < .001. 
     - "0.000" just means it is 0.00049999... or smaller, and rounded to 0. 
     - Values with an e or x like "4.835312e-04" 
   - In APA style, there is no leading 0 in a p-value because it cannot be greater than 1. 

3. Post-Modern: Confidence Interval

|                  | **Calculated Value** | **Reject Null if** | **Decision Criteria** |
| ---------------- | -------------------- | ------------------ | --------------------- |
| **Historically** | \|Test Statistic\|   | **≥**              | Critical Value        |
| **Modern**       | p-value              | **≤**              | alpha [level]         |

Part 4: The Conclusion
----------------------

1. If you ***only*** have a test statistic, look it up on a table that shows which p-values correspond to specific value (e.g., t, F, X2)  
2. If you have a p-value, interpret it like you do all other p-values. The smaller it is, the less likely the difference or relationship you saw was due to random chance. 

​              [![by Randall Munroe, CC BY-NC 2.5](ac3bb844093162365e72e1a26fb733bf.png)](http://xkcd.com/1478/)by Randall Munroe

When the **p-value** is smaller than the **alpha** (a) **level**, we say that the difference or relationship is **statistically significant**. Do NOT use the word "significant" in any other context!

If  **p ≤ a** (.05) then…

-   an effect as large (or larger) than the one you found is unlikely to occur
    by chance if there were no such effect in the population.
-   Describe the test as “statistically significant”
-   Reject **H0**, the null hypothesis, which said there is no effect
-   Accept **Ha,** the alternative Hypothesis, which said there is an effect
-   Conclude that there *is* a difference or relationship

If p \> a then…

-   Describe the test as “not statistically significant”

-   Accept **H0 ,** (there is no effect)

-   Conclude that there is not enough evidence to say there is a difference or
    relationship

Why might this happen? The effect ("signal") isn't large enough, there is too
much variation ("noise"), or there is too little data (small n). With a very
large sample, even small effects will be statistically significant.

![](8d14ab776d414326f9a0250e6cc6c948.png)



[Image by Kevin Clay](http://www.pinterest.com/pin/546905948469906314/)



## More about the Alpha Level

Alpha level / significance level

-   Chicken Little made a bad inference when an acorn fell on his head.

-   By requiring a p-value less than .05, we ensure that there is only a 5%
    chance or less of being like Chicken Little (e.g., saying the sky is falling
    when it isn’t).

-   In some fields, like health or physics, a smaller p-value is used. This
    requires more evidence of an effect.

-   P-values are NOT about the chance the sky is actually falling.  
    (*for more on actual likelihood, see Bayesian Statistics*)