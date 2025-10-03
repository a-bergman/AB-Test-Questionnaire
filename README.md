# Problem Statement

This data set is from [Kaggle](https://www.kaggle.com/datasets/osuolaleemmanuel/ad-ab-testing/data).

When testing out new features for release, business must run an A/B test. In this case, an advertising agency is testing out 2 questionnaires: we want to know if the original or a new format is better.a

# What Is An A/B Test And Why Run One?

Simply put, an A/B test is a way of comparing two versions of any kind asset to determine which performs better.

A/B testing typically is part of a larger pipeline (randomization, observation, data collection, and analysis against KPIs), but for this experiment we only have the collected data.

# Procedure

Our testing is composed of multiple parts:

- Data exploration
- Data cleaning
- Data visualizations
- Statistical testing
- Drawing conclusions

# Hypotheses

H<sub>0</sub>: There is no difference between our control and treatment groups

H<sub>A</sub>: Our treatment group performed better than our control group

# Results & Conclusions

After cleaning our data, we ran 3 tests:

- χ<sup>2</sup> Test Of Independence
- T-test For Means
- Z-test For Proportion

Our Results:

| Test          | Score   | P-value | Alpha | Reject? |
|:--------------|:-------:|:-------:|:-----:|:-------:|
| χ<sup>2</sup> | 0.3465  | 0.5561  | 0.05  | No      |
| T-test        | 0.6453  | 0.5189  | 0.05  | No      |
| Z-test        | -0.6457 | 0.5185  | 0.05  | No      |

We also calculated a confidence interval: -0.037 to 0.073

We failed to reject our null hypothesis for 2 reasons: our measured p-values are all greater than our alpha and our confidence interval contains 0.

Because of our failure to reject the null, the advertiser should not proceed with implementing the change.

# Concerns

We have two primary concern about the data: the experiment was run for 8 daysonly about 15% of IDs in the data set actually responded meaning that we are missing out on a significant amount of data. 

- We would like to rerun the experiment with a larger number of responses because biases may have been introduced by using a subset;
- A longer duration would give us a better representation of actual consumer behavior;
- There seem to be unusual spikes in the experiment day and hour, which suggests to us there may have been an instrumentation error during data collection.
