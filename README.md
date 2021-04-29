Reducing Employee Churn: A data-Science Approach
![image](https://user-images.githubusercontent.com/17712770/116509418-1b26c680-a878-11eb-8b03-7553391902fa.png)

**To understand how to stop a wave of departures from happening, 
we first need to understand why waves happen in the first place**

we mounted a study to investigate the motivations of employees to stay or leave and reasons behind It. This data was then fed into a Random Forest Classifier for training. 

“ Our main aim is to develop an automatic system that takes survey forms from employees and figure out if employee is dissatisfied and has intent to leave and the reason that is making him/her do so, then organization can act to reinforce the right reasons to make them stay and stop reinforcing the wrong reasons.  “

In other words, they can take a positive approach to managing retention in present , which will be more effective over the long run than the ordinary approach of  simply conducting the exit interview in order to hope for  reducing future turnover so that others don't leave. 


## Introduction
Corporate leaders often proclaim that their employees are their most valuable asset. They are the most essential contributors toward profits and shareholder value. While every team and company is unique in some ways, each face the problem of employee churn. Employee churn is basically voluntary or involuntary departures of workforce.This is also called as employee turnover. It barely matters if a company’s employee turnover is above or below average, its workforce becomes temporarily less efficient every time someone leaves. In most companies When an employee leaves, there’s an exit interview to know why employees are leaving and hoping to make changes that might minimize churn in the future. In some other companies surveys are done each month and variety of questions are asked about how they are doing, things going on in the company, and so on. A team will read the anonymous answers, and try to resolve the common issues stated by majority. However This method is not personalized. We need a proactive measure to find out who is having intent to leave and then figure out a way to make them stay. Retaining Talent Is More Cost Effective Than Hiring.It’s not enough to just recruit the top talent. 

## Why we need an employee retention system : 
Retaining Talent Is More Cost Effective Than Hiring.It’s not enough to just recruit the top talent – the real ROI in recruitment comes in retaining those top performers for years to come.

This data science approach to predict if an employee is trying to quit by his survey responses has the following Advantages: 

**1) Reduction In The Cost of Employee Turnover :**
Hiring a new employee is costly it includes advertising, interviewing, screening, hiring and on-boarding costs.
The average replacement cost of a salaried employee to be six to nine months’ salary or 16 percent of annual salary for high-turnover, low-paying jobs (earning under $30,000 a year). 
Retaining existing talent is much more cost efficient.

**2) Overhead to existing employees:**
Before the new employee is hired, though, the open position will probably be covered by other employees, diverting them from their regular work or requiring overtime. 
Or activity is simply not done. If it’s a sales position, that’s a direct hit to the top line. Longer lead times on products could be costly as well.

**3) Tarnished company image:** 
It’s the satisfaction level of your employees that matters the most. So, if an employee isn’t happy, she might spread a negative word about the organization, even after leaving it. 
What’s more, is that an unhappy employee will lack motivation and will not perform well, leading to unsatisfactory performance. This results in unachievable performance targets, low profits, and employee churn. 

**Questions this project aims to answer:**

1)What factors are leading Employee to dissatisfaction and might make him leave in the near future?

2)Can these factors be analysed beforehand and proactive measures can be taken to help reduce employee turnover?

## Methodology:

**1) Data Collection:**
Dataset used: IBM Attrition dataset available on Kaggle
The dataset consists of 1470 records and 35 variables, 
The target variable is “Attrition”
Some of the features are: business travel, income, education. Job roles, overtime, stock-option-level, years with current manager , education etc:
         Model Used: Random Forest
         Evaluation Metrics: confusion matrics, roc_auc score
         IDE : anaconda (jupyter notebooks)

**2) Data Cleaning**
1) First we checked for missing values(nan, 0 or any other value by checking unique value counts): None
2) we checked outliers: none
3) visualised correlation between variables:

  a) There is a high correlation between "joblevel" and "monthly income". which is plausible as higher your job level, higher income you get..another good correlation is between job level and total working years (more experience tends to better level and hence better monthly income)
  
  b) columns such as Employeecount, Over18, StandardHours has same value for all employees with no new value so dropped those columns
  
  c) just 2 values for performance rating....most people got 3 (3---4)
  
  d) people with no stock option have higher attrition..
  
  e) attrition is high in employees in their first year of joining, then it again increases around 5th year. and then goes down after 10 or 11 years of work experience
  
  f) Age data for attrition is right skewed..people in their early career leave jobs more often as compared to later ones.. attrition is high around age 27-30.
  
  g) Most of the people left job either the same year they got promoted or just an year after that.
  
4) converted categorical variables to numerical variables using one hot encoding.

**3) Data Exploration**
![image](https://user-images.githubusercontent.com/17712770/116511548-73ab9300-a87b-11eb-8526-bd2c5501d5be.png)
There is a high correlation between "joblevel" and "monthly income". which is plausible as higher your job level, higher income you get..another good correlation is between job level and total working years (more experience tends to better level and hence better monthly income)

![image](https://user-images.githubusercontent.com/17712770/116511612-8b831700-a87b-11eb-990f-eee3bca215e7.png)

**4) Data Modelling:**
model--Random Forest:
Best Parameters--{'min_samples_split': 2, 'max_depth': 100, 'max_features': 'sqrt', 'n_estimators': 4342, 'min_samples_leaf': 1, 'bootstrap': True}
Hyperparameter Tuning : RandomisedSearchCV

**5) Model Evaluation**
Accuracy Score= 0.8724279835390947

Confusion Matrix: 
![image](https://user-images.githubusercontent.com/17712770/116512003-31368600-a87c-11eb-8c51-d37471be97ba.png)

Roc_auc_score: 0.7988667582417581
![image](https://user-images.githubusercontent.com/17712770/116512151-6e9b1380-a87c-11eb-8f5f-07881af60e3e.png)

### Feature Importances:

![image](https://user-images.githubusercontent.com/17712770/116514368-c6874980-a87f-11eb-9427-c92653498029.png)

## Conclusion:

Retaining existing talent is more  economical and good in building a company image. In other words, through this we can figure out what factors are causing employee attrition and then we can take a positive approach to managing retention in present , which will be more effective over the long run than the ordinary approach of  simply conducting the exit interview in order to hope for  reducing future turnover so that others don't leave. This was a single class classification task. since attrition is something that cannot be verified instantly. If our model predicts a  customer / employees going to leave..it doesnt mean its going to happen soon. It just gives us a probability there is a chance they might. So here we arent concerned with accuracy score as much as with factors that are leading them to drop off/ causing some sort of employee dissatisfaction. Once we figured out what those factors are we can make efforts to reduce employee turnover by addressing those concerns and boost our employees productivities. 






