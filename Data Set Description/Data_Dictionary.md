

## Relevant Information
This dataset is based on "[Bank Marketing](http://archive.ics.uci.edu/ml/datasets/Bank+Marketing)" UCI dataset and is publicly available for research. The details are described in <a href="#readme-citation">[Moro et al., 2014]</a>.

* Number of Rows: 41188
* Number of Columns: 21

### Input variables:
| Tables        | Description | Datatype   |  Values   |
| ------------- |-------------|------------|-----------|
| age           |             | numeric    |           |
| job           | type of job | categorical|{"admin.","bluecollar","entrepreneur","housemaid","management","retired","self-employed","services","student","technician","unemployed","unknown"}|
| marital |  marital status     |   categorical | {"divorced","married","single","unknown"}; note: "divorced" means divorced or widowed |
| education | level of education | categorical | {"basic.4y","basic.6y","basic.9y","high.school","illiterate","professional.course","university.degree","unknown"}|
|default|has credit in default?|categorical|{"no","yes","unknown"}|
|housing|has housing loan?|categorical|{"no","yes","unknown"}|
|loan|has personal loan?|categorical|{"no","yes","unknown"}|
|contact|contact communication type with the last contact of the current campaign|categorical|{"cellular","telephone"}|
|month|last contact month of year|categorical|{"jan", "feb", "mar", ..., "nov", "dec"}|
|day_of_week|last contact day of the week|categorical|{"mon","tue","wed","thu","fri"}|
|duration|last contact duration, in seconds|numeric|Important note:  this attribute highly affects the output target (e.g., if duration=0 then y="no"). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.|
|campaign|number of contacts performed during this campaign and for this client|numeric|[1 to 56]|
|pdays|number of days that passed by after the client was last contacted from a previous campaign|numeric|999 means client was not previously contacted|
|previous|number of contacts performed before this campaign and for this client|numeric|0,1,2,3,4,5,6,7|
|poutcome|outcome of the previous marketing campaign|categorical|{"failure","nonexistent","success"}|
|emp.var.rate|employment variation rate - quarterly indicator|numeric|[-3.4 to 1.4]|
|cons.price.idx|consumer price index - monthly indicator|numeric|[92 to 95]|
|cons.conf.idx|consumer confidence index - monthly indicator|numeric|[-26 to -51]|
|euribor3m|euribor 3 month rate - daily indicator|numeric|[0 to 5.1]|
|nr.employed|number of employees - quarterly indicator|numeric|[4963 to 5228]|
|y|has the client subscribed a term deposit?|binary|{"yes","no"}|

### Missing Values:
Missing Attribute Values: There are several missing values in some categorical attributes, all coded with the "unknown" label. These missing values can be treated as a possible class label or using deletion or imputation techniques. 

## Data Set Citation
<a name="readme-citation">S. Moro, P. Cortez and P. Rita. 2014. "A Data-Driven Approach to Predict the Success of Bank Telemarketing. [dataset]," Retrieved from Decision Support Systems [distributor] V2, http://dx.doi.org/10.1016/j.dss.2014.03.001, 2023-02-05.</a>

**Created by**: Sérgio Moro (ISCTE-IUL), Paulo Cortez (Univ. Minho) and Paulo Rita (ISCTE-IUL) @ 2014
