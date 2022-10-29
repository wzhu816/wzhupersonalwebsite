---
author: Wenjia Zhu
categories:
- Econometrics
date: "2022-10-29"
draft: false
excerpt: Starting with this blog, I'll publish a series of blogs demonstrating some important concepts in the econometrics. I'll begin with the randomized controlled trial (RCT) to explain what it is and why we would encounter selection bias.
layout: single-sidebar
subtitle: 
tags:
- RCT
- Selection Bias
- ATE
title: Econometric Series I – Randomized Controlled Trial (RCT)
---

We always encounter situations when we need to assess the effectiveness of a "treatment". In clinical research, we want to evaluate the effectiveness of a drug in curing disease and relieving suffering. In school, we could be interested in understanding how likely participating in study groups can improve students’ academic performance. In the energy field, we are curious about the savings outcome from a utility’s energy efficiency program. All these questions can be answered by economic evaluations, which explains the causal effects from explanatory variables on outcome. A randomized controlled trial, also known as RCT, is such an experimental form of impact evaluation.

---

## What is RCT?

A randomized controlled trial (or randomized control trial, RCT) is a form of scientific experiment that randomly assigns the same eligible population into an experimental group or a control group. The distinguishing feature of an RCT is the random allocation of the units receiving the program or policy intervention[^rct]. The only expected difference observed between the experimental and the control groups is the outcome variable being studied[^diff]. In a randomized trial, the average treatment effect (ATE) can be estimated by comparing the mean outcomes for experimental (treated) and the control (untreated) groups[^ate].

## Advantages and Disadvantages
The major advantage of RCTs is that the randomization minimizes the bias and confounding factors and therefore can investigate the cause-effect relationships. However, conducting RCTs in real life could be cumbersome. One of the noxious disadvantages that the RCTs have is the long time and high costs. RCTs are usually very expensive to undertake, and the effect of treatment could take a long time to observe. In some research, especially in clinical trials or social science, the research method can also come with some ethical limitations.    

## Selection Bias
Ideally, we can investigate a causal effect based on the experimental data from experiments designed specifically for a treatment or policy evaluation. But in most of the applications, we normally estimate causal effects from the observational data, also known as nonexperimental data, which are collected from surveys or use historic records. The main concern of using observational data is that the “treatment” now is not randomly assigned. In most cases, people are self-selected to the program, which means there could be known or unknown factors that correlate with both the treatment variable and the outcome variable. The phrase “selection bias” refers to the distortion of a statistical analysis that fails in proper randomization so that the collecting samples are not representative of the population intended to be analyzed[^bias]. 

## The Impact of Selection Bias
The selection bias affects internal validity for the statistical model. As discussed earlier, the average treatment effect (ATE) can be estimated by comparing the mean outcomes for treated and untreated groups. If there are selection bias between treated and untreated units from the observational data, the ATE we estimate could include the selection bias and therefore the result is not the true causal. Let’s write it out in equation:

Let `E[·]` denote the mathematical expectation operator, then we will have
$$
E[Y_i|D_i=1] - E[Y_i|D_i=0]
$$
$$
= E[Y_{1i}|D_i=1] - E[Y_{0i}|D_i=0]
$$
$$
= E[Y_{1i}|D_i=1] - E[Y_{0i}|D_i=1] + E[Y_{0i}|D_i=1] -  E[Y_{0i}|D_i=0]
$$
$$
= E[Y_{1i} - Y_{0i}|D_i=1] + selection\ bias
$$

The first expectation term is defined as the average treatment effect on the treated (ATT), which can be proved to be the same as the average treatment effect (ATE) for most of the cases. Here, we regard it as a true causal effect. And the second expectation term is denoted as selection bias. Based on the equation, the difference in outcome between the treatment group and control group equals ATT only when selection bias is zero.

One step further, we can also draw conclusions on the selection bias direction and how the bias impacts estimation of the true causal effect. If the selection bias is positive, we deem it as a positive selection bias. If the selection bias and the ATT share the same sign, the observed difference is an overestimation of the true treatment effect.






[^rct]: UNICEF, Randomized Controlled Trials (RCTs). https://www.unicef-irc.org/KM/IE/impact_7.php
[^diff]: The Himmelfarb Health Sciences Library, Randomized Controlled Trial. https://himmelfarb.gwu.edu/tutorials/studydesign101/rcts.cfm
[^ate]: Wikipedia, Average treatment effect. https://en.wikipedia.org/wiki/Average_treatment_effect
[^bias]: Wikipedia, Selection bias. https://en.wikipedia.org/wiki/Selection_bias

