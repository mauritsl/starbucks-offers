This project analyses Starbucks offers.
A write-up of this analysis is available as [blogpost on Medium](https://medium.com/@maurits_94643/you-are-part-of-an-experiment-this-is-what-companies-learn-from-you-5050142f2891).

## Questions answered

* Which offers are used?
* Which parameters should be changed to increase its usage or turnover?
* Can we link the perceived effects to demographic features? Thus, what offers work best for which people?

## Files

* `starbucks.ipynb` contains the Python notebook containing all steps and further explanation for this analysis
* `tree/*.dot` are the outputs from the decision trees
* `tree/*.png` are the rendered outputs

## Used libraries

The following libraries are required to run the notebook:

* matplotlib
* numpy
* pandas
* scipy
* seaborn
* sklearn

## Motivation

This project was done as part of Udacity’s Data Science Nanodegree course. 

Getting more information from a few dimensions makes this an inspiring project as well because it requires a creative and flexible approach. There are no basic modelling techniques that can handle this data directly. A custom method was needed to know if an offer was used, the change in turnover, and the number of offers seen before.

## Summary

Starbucks wants to know what offers works best and why. An experiment was set up with three different offer types: discounts, buy-one-get-one (bogo) and informational. Each class has multiple configurations that differ in duration, reward (earnings when completing) and difficulty (minimum spending). In total, there were ten settings. The available demographic features are age, income and gender. This information has to be combined with the transaction data to gain useful insights about which offers work, and what factors account for that.

The following recommendations can be made on the offers:

* Prefer discounts over bogo's. Discounts are more likely to be used.
* Favor web orders over mobile. Web orders are more likely to be used.
* Stop discount 2298..b8c2, because it seems to have a (relative) adverse effect on the turnover.
* Consider to stop bogo's 4d5c..8da0 and f194..e20d.
* Limit duration to 7 days. Offers that are valid for more than seven days tend to be used less.

There were some observations about demographic features. These are:

* Females prefer discounts over bogo's
* For males, avoid bogo's with rewards above 7.5

Both findings are not statistically significant. However, we might still implement the decision tree to determine if we should send an offer. This model includes these findings. It can predict if an offer will be used with 68% accuracy, which is better than the current (naive) model that sends an offer to everybody. Only 59% of the offers were used, which is also the accuracy of this naive model. Therefore, it seems reasonable to implement this decision tree, to avoid irritating users with offers they will not use.
