<a name="readme-top"></a>
![Bitbucket open issues](https://img.shields.io/bitbucket/issues/clkride/Feature_Importance_ANN?style=flat-square)
![GitHub commit activity](https://img.shields.io/github/commit-activity/m/clkride/Feature_Importance_ANN?style=flat-square)
![GitHub contributors](https://img.shields.io/github/contributors/clkride/Feature_Importance_ANN?style=flat-square)
![GitHub watchers](https://img.shields.io/github/watchers/clkride/Feature_Importance_ANN?style=flat-square)
![GitHub Repo stars](https://img.shields.io/github/stars/clkride/Feature_Importance_ANN?style=flat-square)
![GitHub](https://img.shields.io/github/license/clkride/Feature_Importance_ANN?style=flat-square)
<a href="https://linkedin.com/in/abbas-singapurwala">
<img src="https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin&labelColor=blue">
</a>

# Feature_Importance_ANN
Aim - 
1. To find key drivers that influence the output of an Artificial Neural Network
2. To determine the relative importance of these influencing factors

## Table of Contents
- [Project Description](#project-description)
- [About Data Set](#about-data-set)
- [Data Exploration](#data-exploration)
- [Modeling Approach](#modeling-approach)
- [Model Performance](#model-performance)
- [Feature Importance](#feature-importance)
- [Summary](#summary)
- [Author](#author)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Project Description
The bank in this case wants to predict whether a customer will subscribe to a term deposit. To make this a successful telemarketing campaign, the Bank would like to know which customers are highly likely to subscribe its offer. <br/><br/>
The dataset provided by the bank contains details on the number of days since last contact which captures recency aspect and the number of contacts performed during the present and the previous campaign which captures the frequency aspect of the marketing campaign. <br/><br/>
For modelling purpose, I have used the recency and frequency metrics to train my model because these metrics have very high predictive power. As for the model, I have used a binary classifier which gives an output of either 1 (the customer will subscribe) or 0 (the customer will not subscribe). 
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## About Data Set

* Title: Bank Telemarketing (with social/economic context)
* Past Usage: The full dataset ([bank-additional-full.csv](https://github.com/clkride/Feature_Importance_ANN/blob/main/Data/bank-additional-full.csv)) was described and analyzed in:

  S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems (2014),doi:10.1016/j.dss.2014.03.001.
 
 * All records are ordered by date (from May 2008 to November 2010). Detailed Description can be found @ [Data_Dictionary.md](https://github.com/clkride/Feature_Importance_ANN/blob/main/Data%20Set%20Description/Data_Dictionary.md).

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Data Exploration

In this phase of the project, I have tried to resolve common data challenges faced such as poor data quality, multicolinearity, and correlation between pair of variables. The key insights are as follows - 

Insight| &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; Visualization &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;
:-------------------------|:-------------------------:
 Plot1: Duration of call v/s Subscription <br/> <br/> Higher is the duration of the last call,<br/> higher is the probability that the client will subscribe | ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/images/duration.png?raw=true)
  Plot2: Histogram of Duration with Subscription Overlay <br/> <br/> Subscription declines when the duration of call<br/> is close to 50 min. However, the outcome is most <br/>certainly 'yes' if the duration is close to 65 min. <br/>and 'no' when the duration exceeds 65 minutes. | ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/images/duration_limits.png?raw=true)
 Plot3: Months v/s Subscription <br/> <br/> Campaigns are most successful in months of - <br/> Dec, Mar, Oct, and Sep. | ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/images/months_vs_campaign_outcome.png?raw=true)
 Plot4: Job Type v/s Subscription <br/> <br/> Surprisingly, students and retired people are<br/> more likely to subscribe for a term deposit. | ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/images/job_type_vs_subscription.png?raw=true)
 Plot5: Previous Outcome v/s Current Subscription <br/> <br/> If the outcome of previous campaign was a success <br/> then the propensity of that client to subscribe <br/> the term deposit is fairly high. | ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/images/prev_outcome.png?raw=true)
 Plot6: Education Level v/s Subscription <br/> <br/> Illiterate people are more likely to subscribe than <br/>educated folk. Also, as the level of education <br/>increases the propensity to subscribe increases as well.| ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/images/edu_vs_subscription.png?raw=true)

From the preliminary data analysis, I concluded that the duration of the last call, outcome of the previous campaign, and month in which the customer was contacted have significant impact on the final outcome. However, there is no way to conclude which one is more or less important relative to each other.

Detailed Description can be found @ [Bank_Marketing_Exploratory_Analysis.ipynb](https://github.com/clkride/Feature_Importance_ANN/blob/main/Bank_Marketing_Exploratory_Analysis.ipynb).

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Modeling Approach

Steps - 
1. Feature Engineering and Data Transformation of Categorical and Numerical Attributes
2. Split the dataset into predictors and response variables. In this case, response is whether customer subscribes or not.
3. Split the dataset into training set (75%) and test set (25%) 
4. Create Model 
5. Fine tune the Hyper-parameters
6. Test Performance of the Final Model
7. Report Performance Metrics
8. Identify most important factors based on socioeconomic characteristics of the customers

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Model Performance
Overall, our model has achieved an accuracy of 91.66% for the test set.

The confusion matrix for this classification model is shown below.<br/> <br/>
Confusion Matrix           | &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; Performance Metrics &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;
:-------------------------:|:-------------------------
![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/images/confusion_matrix.png?raw=true)| Number of False Positives, FP = 438 <br/> Number of False Negatives, FN = 392 <br/> Number of True Positives, TP = 664 <br/> Number of True Negatives, TN = 8457 <br/><br/> False Positive Rate (FPR) = FP / (FP + TN) = 0.0492 <br/>False Negative Rate (Type2 Error)= FN / (FN + TP) = 0.3712<br/>True Positive Rate (TPR) = TP / (TP + FN) = 0.6287<br/>True Negative Rate (Type1 Error) = TN / (TN + FP) = 0.9507<br/>Accuracy = (TP + TN) / (TP + TN + FP + FN) = 0.9165

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Feature Importance
SHAP Values           | &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; Explanation &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;
:-------------------------:|:-------------------------
![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/images/relative_importance.png?raw=true)| The horizontal bar plot shows the average impact of<br/> a feature on model output.<br/><br/> Here, duration of the last contact, number of <br/>employees, and whether the last contact month<br/> of the year was May or not contribute the most in estimating<br/> customer subscribription rate for a term deposit.<br/><br/>SHAP values measure feature importance at row<br/> level. It represents how a feature influences the<br/> prediction of a single row relative to the other<br/> features in that row and to the average outcome<br/> in the dataset. Features are ranked in the<br/> diminishing order of influence. The size of the bar<br/> plot shows the magnitude of the influence that <br/> feature  has on the final outcome.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Summary
* Optimal Set of Hyperparameters for our Neural Network is given by -
  * neurons = 31
  * learning_rate = 0.1
  * batch_size = 2048
  * optimizer = adam
  * epochs = 100
  * Accuracy = 91.65%
* Precision for (y=0) = 95%
* Precision for (y=1) = 63%
* Duration of last contact is the most influencing factor in determining whether a customer will subscribe to a term deposit.
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Author
 @[Abbas S.](https://github.com/clkride)

## License
The MIT License (MIT)

Copyright (c) 2023 Abbas Singapurwala

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments
Inspiration, code snippets, etc.
* [Choose an Open Source License](https://choosealicense.com)
* [Img Shields](https://shields.io)
* [GitHub Pages](https://pages.github.com)
<p align="right">(<a href="#readme-top">back to top</a>)</p>





