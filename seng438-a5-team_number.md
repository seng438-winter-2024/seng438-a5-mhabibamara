**SENG 438- Software Testing, Reliability, and Quality**

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#:       |   |
|-----------------|---|
| Student Names:  |   |
|                 |   |
|                 |   |
|                 |   |

# Introduction

# 

# Assessment Using Reliability Growth Testing 
For this section, our group chose to work with the C-SFRAT testing tool to test the test data file "CDS.DAT" under the Failure_Count directory. The following models were compared to determine which one aligned/fit mostly with our input failure data:
- IFR Salvia & Bollinger
- IFR generalized Salvia & Bollinger
- S Distribution
- Discrete Weibull (Order 2)
- Discrete Weibull (Type III)
- Geometric
- Negative Binomial (Order 2)
- Truncated Logistic

In the below chart, we can see the original failure and model reliability plot against our two covariates (T,F and (E,F)):
![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/a4e2ba01-21af-4ca2-8f74-3dd762683f65)

To compare the models, we simply selected the Model Comparison tab which gave us a table with a list of all models. The top two models are the ones we want to look at:
![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/24e09638-5d89-433f-aa32-607f7125f6c6)
Sorting by log-liklihood, gives us the models in order of how cloself they fit with our failure data. So in our case, DW3(E) and DW3(F) were the closest models to our failure data. 

The Discrete Weibull (DW3) is particularly applicable for modeling failure data measured in discrete units like cycles or shocks. This distribution provides a versatile tool for analyzing scenarios where the timing of events is counted in distinct intervals, making it distinctively useful in fields that deal with discrete data patterns and reliability analysis.


# Assessment Using Reliability Demonstration Chart 

# 

# Comparison of Results

# Discussion on Similarity and Differences of the Two Techniques

# How the team work/effort was divided and managed

# 

# Difficulties encountered, challenges overcome, and lessons learned

# Comments/feedback on the lab itself
