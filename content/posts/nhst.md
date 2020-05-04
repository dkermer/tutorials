---
title: "Null Hypothesis Significance Testing"
date: 2020-04-21T13:48:12-04:00
draft: true
---

Null Hypothesis Significance Testing (NHST) is a common way of doing statistical analysis. It can seem complicated, but much of that goes back to the way it had to be done before computers. 

<!--more-->

## Part 1: The Test

Which [statistical test you use](http://guides.nyu.edu/quant/choose_test_1DV) will depend on the hypothesis (difference vs relationship), data (independent vs paired), how many variables are involved, and their level of measurement (categorical vs quantitative). Tests that compare just two groups, such as t-tests, can be one [1 or 2-tailed](https://www.graphpad.com/guides/prism/8/statistics/one-tail_vs__two-tail_p_values.htm), depending on whether you want to test if a particular group mean is larger, or just whether there is a difference.

Each test will make use of a different **summary statistic** from your data to see if it matches expectations or not. Tests for numeric variables are often about the means of one or more populations (μ), or a coefficient (ex. β). Tests for categorical variables may compare proportions (p) or frequencies in groups (ex. f<sub>e</sub>). 

Each test will also produce a different **test statistic**, which will be an indication of how much evidence your data provides for the difference or relationships you think exists. Test statistics are repesented by a letter or greek symbol, most commonly: Z, t, F, or Χ<sup>2</sup>. 

Part 2: The Hypotheses
----------------------

If you don't have a **Null Hypothesis**, you are not doing NHST. It states that the *summary statistic* (average, proportion, observed values, or coefficient) relating to the *population* your data is from equals* a specified value (or another calculated value). If the logical expression is true, the difference or relationship you seek does *not* exist. The symbol you use represents your summary statistic and depends on the statistical test you will use. Often the comparative values is 0, but it may not be (here, the example is 10). 

The **Alternative Hypothsis** is what you would actually like to be true. Just write the opposite of the Null Hypothesis (**=** to  **≠**,  **≤**  to **<**, and **≥** to **>**).

**Null Hypothesis H<sub>0</sub>**

​	*examples*:  μ **=** 10    μ **≤** 10    μ **≥** 10   β **=** 0	r **=** 0	μ<sub>1</sub> **=** μ<sub>2</sub>      f<sub>e</sub> **=** f<sub>o</sub>
​						*always includes an equals sign*

-   The status quo
-   "No true difference" *or* "No true relationship"
-   "Any relationship or difference in the sample due to chance"

**Alternative Hypothesis H<sub>a</sub> **

​	*examples*: μ **≠** 10   μ **\>** 10   μ **\<** 10	β **≠** 0	r **≠** 0	μ<sub>1</sub> **≠** μ<sub>2</sub>      f<sub>e</sub> **≠** f<sub>o</sub>
​						*does not include an equals sign* 

-   What you really think and want to convince others of
-   What you can get published
-   "There is a difference" *or* "There is a relationship"

Part 3: The Data
----------------

The question is now whether your data makes the Null Hypothesis too unlikely. Rember that the data is a sample and your Null Hyptohesis is about the population. 

Start by calculating the **summary statistic** your Hypotheses refer to, and create **charts or graphs** to look for the difference or relationship you think should be there. If you do not see the difference or relationship you are trying to show (the Alternative Hyothesis), it does not matter what the p-value is. 

Have your computer **perfom the test** you selected If the visualization shows a possible relationship or difference. The computer will produce a lot of output, but much of it represent calculations the computer made in order to show you the p-value. But first, **check the sample size**, which might be specified separately, but can be inferred from the values labeled df. You want to make sure that you have approximately the number of cases you expect. 

There will be one overall **p-value** for any given statistical test. Sometimes there are follow-up ("Post Hoc") or sub-tests (individual coefficients) that test additional questions. To find p-values, look for labels like these:
	`Significance` 	`Sig.`	`Prob`	`Pr =`	`P > |t|`	`Pr > ChiSq`	`Prob > F` 

The **test statistic** itself has no inherent meaning, it is simply used to determine if the test is statistically significant (the larger or farther from 0 it is, the lower the p-value). But, you will need it to report the test results. Note that it is possible to compute a test statistic by hand (though it can take a while). However, converting the test statistic to a p-value does need a computer or a really good mathematician. The conversion is different for each test statistic since they each have a different distribution.   

Also look for measures of **Effect Size**, which is a standardized way to measure the amount (or extent) of the difference or relationship. [explain]

## Part 4: The Decision

The process of drawing a conclusion has changed as computers have become more widely available and powerful. However, some instructors still teach the old method because that is how they were taught and it can help some people to understand the process. I think that is unnecessary. 

So, historically, researchers would use standard tables to convert their desired p-value cutoff (e.g., .05) to a "critical value" that they could compare to their test statistic. These days, we just compare the calculated p-value to our desired cutoff directly.   / If you ***only*** have a test statistic, look it up on a table that shows which p-values correspond to specific value (e.g., t, F, X<sup>2</sup>)  

Modern: P-Value / probability value. If you have a p-value, interpret it like you do all other p-values. The smaller it is, the less likely the difference or relationship you saw was due to random chance.  But, with computers, we can get an exact
p-value for our specific data. A p-value puts the value of the test statistic on a common and interpretable scale.

- When p-values are less than .001, they are just reported as "**p < .001**". These also should be reported as p < .001 : 
  - "0.000" just means it is 0.00049999... or smaller, and rounded to 0. 
  - Values with an e or x like "4.835312e-04". This is scientific notation and it only displays if the value would round to "0.000" . 
- In APA style, there is [no leading 0](https://blog.apastyle.org/apastyle/2010/07/a-post-about-nothing.html) in a p-value because it cannot be greater than 1. 

Post-Modern: Confidence Interval

|                  | **Calculated Value** | **Reject Null if** | **Decision Criteria** |
| ---------------- | :------------------: | :----------------: | :-------------------: |
| **Historically** |  \|Test Statistic\|  |       **≥**        |    Critical Value     |
| **Modern**       |       p-value        |       **≤**        |     alpha [level]     |
| **Post-Modern**  | Confidence Interval  |       **≠**        |  H<sub>0</sub> value  |



When the **p-value** is smaller than the **alpha** (a) **level**, we say that the difference or relationship is **statistically significant**. Do NOT use the word "significant" in any other context!

![Pimp Meme: "If the 'P' is Low Then the Ho Must Go" -- Image by Kevin Clay](8d14ab776d414326f9a0250e6cc6c948.png)



[Image by Kevin Clay](http://www.pinterest.com/pin/546905948469906314/)

## Part 5: The Conclusion

​              [![XKCD P-Value Interpretation Chart by Randall Munroe, CC BY-NC 2.5](ac3bb844093162365e72e1a26fb733bf.png)](http://xkcd.com/1478/)by Randall Munroe

If  **p ≤ a** (.05) then…

-   an effect (difference or relationship)
    -   as large (or larger) than the one you found in your sample 
    -   is sufficiently unlikely to occur 
    -   simply because you randomly selected an usual sample  ("by chance")
    -   if there were not at least some effect in the population
-   Describe the test as “statistically significant”
-   Reject **H<sub>0</sub>**, the null hypothesis, which said there is *no* population effect
-   Accept **H<sub>a</sub>,** the alternative hypothesis, which said there *is* a population effect
-   Conclude that there *is* a difference or relationship
-   With a very large sample, note that even small effects will be statistically significant. Be very careful making a big deal out of a tiny difference just because it is. 

If p \> a then…

-   Describe the test as “not statistically significant”
-   Accept **H<sub>0</sub> ,** (there is no effect in the population)
-   Conclude that there is not enough evidence to say there is a difference or
    relationship in the population
    -   Why might this happen? The effect ("signal") isn't large enough, there is too
        much variation ("noise"), or there is too little data (small n). 

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