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
- [Author](#author)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Project Description
The bank in this case wants to predict whether a customer will subscribe to a term deposit. To make this a successful marketing campaign, the Bank would like to know which customers are highly likely to subscribe its offer. <br/><br/>
The dataset provided by the bank contains details on the number of days since last contact which captures recency aspect and the number of contacts performed during the present and the previous campaign which captures the frequency aspect of the marketing campaign. <br/><br/>
For modelling purpose, I have used the recency and frequency metrics to train my model because these metrics have very high predictive power. As for the model, I have used a binary classifier which gives an output of either 1 = the customer will subscribe or 0 = the customer will not subscribe. 
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## About Data Set

* Title: Bank Marketing (with social/economic context)
* Past Usage: The full dataset ([bank-additional-full.csv](https://github.com/clkride/Feature_Importance_ANN/blob/main/Data/bank-additional-full.csv)) was described and analyzed in:

  S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems (2014),doi:10.1016/j.dss.2014.03.001.
 
 * All records are ordered by date (from May 2008 to November 2010). Detailed Description can be found @ [Data_Dictionary.md](https://github.com/clkride/Feature_Importance_ANN/blob/main/Data%20Set%20Description/Data_Dictionary.md).

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Data Exploration

In this phase of the project, I have tried to resolve common data challenges faced such as poor data quality, multicolinearity, and correlation between pair of variables. The key insights are as follows - 

Insight           | &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; Visualization &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;
:-------------------------:|:-------------------------:
 Plot1: Duration of call v/s Subscription <br/> <br/> Higher is the duration of the last call,<br/> higher is the probability that the client will subscribe | ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/duration.png?raw=true)
  Plot2: Histogram of Duration with Subscription Overlay <br/> <br/> Subscription declines when the duration of call<br/> is close to 50 min. However, the outcome is most <br/>certainly 'yes' if the duration is close to 65 min. <br/>and 'no' when the duration exceeds 65 minutes. | ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/duration_limits.png?raw=true)
 Plot3: Months v/s Subscription <br/> <br/> Campaigns are most successful in months of - <br/> Dec, Mar, Oct, and Sep. | ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/months_vs_campaign_outcome.png?raw=true)
 Plot4: Job Type v/s Subscription <br/> <br/> Surprisingly, students and retired people are<br/> more likely to subscribe for a term deposit. | ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/job_type_vs_subscription.png?raw=true)
 Plot5: Previous Outcome v/s Current Subscription <br/> <br/> If the outcome of previous campaign was a success <br/> then the propensity of that client to subscribe <br/> the term deposit is fairly high. | ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/prev_outcome.png?raw=true)
 Plot6: Education Level v/s Subscription <br/> <br/> Illiterate people are more likely to subscribe than <br/>educated folk. Also, as the level of education <br/>increases the propensity to subscribe increases as well.| ![alt text](https://github.com/clkride/Feature_Importance_ANN/blob/main/edu_vs_subscription.png?raw=true)

From the preliminary data analysis, I concluded that the duration of the last call, outcome of the previous campaign, and month in which the customer was contacted have significant impact on the final outcome. However, there is no way to conclude which one is more or less important relative to each other.

Detailed Description can be found @ [Bank_Marketing_Exploratory_Analysis.ipynb](https://github.com/clkride/Feature_Importance_ANN/blob/main/Bank_Marketing_Exploratory_Analysis.ipynb).

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Modeling Approach

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





