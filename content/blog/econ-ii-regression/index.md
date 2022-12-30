---
author: Wenjia Zhu
categories:
- Econometrics
date: "2022-12-02"
draft: false
excerpt: In this blog, I'll continue the econometrics session and introduce how we can estimate average treatment effects with regression.
layout: single-sidebar
subtitle: Estimate Treatment Effects with Regression
tags:
- Selection Bias
- ATE
- Regression
- Ignorability of Treatment
- Heterogeneous Treatment Effects
title: Econometric Series II – Regression
---

In the last post, we discussed about randomized controlled trial and introduced the concept of treatment effects. As a reminder, the average treatment effect (ATE) can be estimated by deriving the difference in outcome means from the treated and untreated groups. In this blog, let’s step further into estimating average treatment effects with regression.

---

## Potential outcomes for units

Only one outcome is realized or observed after the intervention, and the other one would be the potential outcome. We denote the observed outcome for a unit `i` as  `$Y_i$`. `$D_i$` is denoted as the treatment received by a unit `i`, which could be 0 or 1, so `$D_i∈\{0,1\}$`. In theory, we would have two potential outcomes: 
+ `$Y_1i$` if the unit received treatment when `$D_i=1$` and 
+ `$Y_0i$` if not (`$D_i=0$`).

The causal effect of receiving treatment for a unit `i` is a comparison of potential outcomes, which is `$Y_1i-Y_0i$`. The definition of causal effects does not depend on the actual treatment or action taken. However, now you probably are noticing that we have a challenge here: in reality, we do not observe both potential outcomes, and we only observe one outcome after a treatment is conducted. We call the other non-observable outcome to be the **“counterfactual”**. 

Now we can rewrite the observed outcome Y_i in terms of the potential outcome as:
$$Y_i=Y_0i+(Y_1i-Y_0i)D_i$$

Please remember that a unit either receives the treatment or not, never both. So, if `$D_i=1$`, then the observed outcome is `$Y_i=Y_1i$` and the counterfactual outcome is `$Y_0i$`, vice versa. 

In my previous blog, I ended with the equation notation of average treatment effect and explained how the selection bias could impact the estimation of ATE. Recall that 
$$E[Y_i│D_i=1]-E[Y_i│D_i=0]=E[Y_1i│D_i=1]-E[Y_0i│D_i=0]$$

The right hand of the equation is comparing the average observed outcomes or conditional expectation. Then it can be further rewritten as:  $$E[Y_1i│D_i=1]-E[Y_0i│D_i=1]+E[Y_0i│D_i=1]-E[Y_0i│D_i=0]$$ 
To interpretate the comparison between observed outcomes `$E[Y_1i│D_i=1]-E[Y_0i│D_i=1]$` as causal effects, we want the selection bias to be zero, which means `$E[Y_0i│D_i=1]=E[Y_0i│D_i=0]=E[Y_i│D_i=0]$`.

---

## Estimation by regression

We know that the linear/Ordinary Least Squares (OLS) model is a conditional expectation function, so we can use a regression model to estimate the treatment effects. Suppose we have the population model:
$$Y_i=β_0+β_1 D_i+ε_i$$

+ So, the expected value of the outcome conditional on treatment is `$E[Y_i│D_i=1]=β_0+β_1+E[ε_i |D_i=1]$`. 
+ The expected value for the control is `$E[Y_i│D_i=0]=β_0+E[ε_i |D_i=0]$`.

The difference between treatment and control is `$β_1+E[ε_i│D_i=1]-E[ε_i |D_i=0]$`. And now `$β_1$` is a measure of treatment effect only if `$E[ε_i│D_i=1]=E[ε_i |D_i=0]$`. The question now becomes when this equivalent holds. <span style="color:brown"><u>The answer is that when treatment assignment `D` is mean independent of the error term, where `ε⊥D`.</u></span>  In this case, both are just `$E[ε_i]$`. **Mean independence** comes up most often in econometrics as an assumption that is weaker than independence but stronger than uncorrelatedness[^mean_independence]. A random variable `Y` is said to mean independent of `X` iff `$E[Y│X=x]=E[Y]$` for all `x` such that the probability mass/density of `X` at `x` is not zero. To make it easier to digest, if the conditional expectation is the same as the unconditional expectation. Overall, independence implies that `D` and εare uncorrelated in any functional form, but mean independence doesn’t imply zero correlation. However, <span style="color:brown">*independence does imply mean independence*</span>.

We can use a regression when the regression model includes all confounders. A confounder is a variable that influences both the dependent variable (outcome) and independent variable[^confounder]. If we leave a confounder, it’s part of the error term `ε`, and this violates the rule of mean independence.

Suppose a confounder variable `V` exists that correlates with both `D` and `Y`. *Let’s make an example, we want to confirm the effectiveness of an online study group on improving students’ exam performance. We want these students with lower mid-term scores have more chances of getting enrolled in the study group. So, we classify students by their mid-term scores, these students with a below 70 score has 67% chances of getting selected, but the other students with a score no less than 70 has 33% chances of getting selected.* On average, the ‘treated’ group now has more students with poor academic performance than the control group. This implies conditional randomization, where the selection bias is not zero, `$E[Y_0i│D_i=1]≠E[Y_0i│D_i=0]$`. Refer to the population model `$Y_i=β_0+β_1 D_i+ε_i$`, academic performance is part of ε and now `$E[ε_i│D_i=1]≠E[ε_i |D_i=0]$`. We can easily fix this issue by adding the academic performance as an independent variable in our regression model:
$$Y_i=γ_0+γ_1 D_i+γ_2 V_i+η_i$$

We use the statistical adjustment method. And now `η` is conditional independence from `D`: `$η_i⊥D_i |V_i$`.

## Ignorability of treatment/ Selection on observables
Let’s revisit the assumption since we’ve justified some type of regression adjustment. Now the assumptions states that conditional on observable covariates `$X_n$`, the assignment of units to experimental groups is independent of potential outcomes:
 $$(Y_0i,Y_1i)⊥D_i |X_ni$$

Where:
 
+ `$Y_0i$`,`$Y_1i$` are the potential outcomes for unit `i`,
+ `D` is treatment assignment,
+ `$X_n$` are a set of `n` observable covariates.

This assumption amounts to assuming ignorability of treatment (given `$X_n$`). If we don’t control for confounders, our statistical model is showing just a correlation but not causation. The error term, `ε`, should be conditional independent. This can be translated into `$E[Y_0i│X_i,D_i=1]=E[Y_i│X_i,D_i=0]$`. In other words, if comparing two units with the same `x` characteristics, the expected outcome under treatment is the same for treated unit as for untreated unit. This is often also described as selection on observables. 

## Heterogeneous treatment effects
In the example of online study group, the treatment effects can be estimated by using the model:
$$Y_i=β_0+β_1 D_i+β_2 V_i+ε_i$$

We will obtain the treatment effect as average across levels of mid-term scores. In theory, we could estimate two models, one from `V=1`, and the other from `V=0`. This is called **stratified models**, and we would get two estimates of treatment effects, `$\hat{β_1}$` if `V=1`, and `$\hat{γ_1}$` if `V=0`. The two coefficients could be different if there is effect heterogeneity. To obtain ATE, we can combine them and weight the coefficients. With the interacted model, we can weight the estimates from the stratified analysis and therefore average over the heterogeneity.
$$Y_i=γ_0+γ_1 D_i+γ_2 V_i+γ_3 D_i×V_i+η_i$$


---

#### ok, that's everything for now...let's take a break and look forward to seeing you in my next blog!

![TIREDDDDD](tired.png)

 
---
Useful References:
1. https://rpubs.com/akhilr/677363
2. https://www.soderbom.net/lecture11_notes.pdf 
3. https://clas.ucdenver.edu/marcelo-perraillon/sites/default/files/attached-files/w2_causal_inference_perraillon.pdf


 


[^mean_independence]: Statistical Odds & Ends, What is mean independence? https://statisticaloddsandends.wordpress.com/2021/12/11/what-is-mean-independence/
[^confounder]:Wikipedia, Confounding. https://en.wikipedia.org/wiki/Confounding


