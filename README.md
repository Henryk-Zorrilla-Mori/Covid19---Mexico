# Covid19---Mexico
## Analysis of Covid-19 cases in Mexico

### ¿What are the columns that you consider important in the document 200504COVID19MEXICO.csv and why? (create a list with those columns and the reason why they are important. Try to investigate the meaning of the columns you don't know).

for col in df.columns:
    print(df[col].value_counts(normalize=True))
    
All the columns are important because the more information the better, but there are some that are more relevant than others. And that's where we're going to focus. On using the most relevant information so as not to use so much data and make the job easier, so we can focus on finding a solution with this data.
What we are going to group in a list some columns that we see that we can apply to people that can be infected by the Covid-19 and thus be able to treat the patient depending if he has some of these diseases that can help the virus to be more aggressive or not.
We will call the list antecedents and put the diseases that the patient could suffer or have had in the past making the patient more vulnerable to contract this virus:

antecedents= df[['NEUMONIA','DIABETES','INMUSUPR','HIPERTENSION','OBESIDAD','CARDIOVASCULAR','RENAL_CRONICA','TABAQUISMO','OTRA_COM','EPOC' ]]


### After reviewing the 3 dataframes, find at least 4 important data that could be obtained through data analysis.

One of the elements we find most interesting is to check which cities do best testing. To do this, we should compare the date of entry (together with the symptoms) and make comparisons with existing municipalities. In this way we can check the date of origin of most cases, thus showing that there are communities that have made more tests (so the cases are greater) compared to others that have dates of admission or more scattered symptoms, which indicates that patients have come to the health center because of their symptoms, and not because of a previous test, in addition to checking whether or not there has been preventive testing.
Another aspect that has attracted our attention is that it has to do with related diseases. To do this, we must compare how much time has passed between the date on which the symptoms appeared and the date of death of the patient. Next, we should check the different diseases of each patient, being these: asthma, obesity, renal / chronic renal, cardiovascular, smoking, immunosuppressed patients, hypertension, diabetes and COPD.
We believe that a comparison could also explain the ICU admissions present in the dataset, and we could even assess the evolution of the disease in pregnant patients.
We can obtain this by analyzing these three Dataframes:
a) Cases of infection by state and municipality, so we can see whether the more people in each municipality the virus is able to spread more quickly or whether more factors such as the history of those affected also play a role.
b) The number of patients in the ICU, and how the health system in each municipality is prepared for this pandemic
c) Date and death of each patient admitted for covid-19 positive
d) The recovery time of each patient depending on whether they had any history


### Find at least 5 graphs you could make with the data and describe the reason for making that graph and with which variables.

After a better analysis of the data, we have decided to keep the second case, which tries to measure the severity of the disease if other previous pathologies of the patient are associated with it. Firstly, we would like to check the alteration in the prognosis that some of the diseases could represent, such as asthma, tobacco addition or having a depressed immune system. In order to analyse these relationships, we would carry out statistical studies for each disease, checking whether or not they accelerate the severity of the patient's condition. A study such as this could focus the attention of health personnel more effectively, by allowing them to know which patients are most at risk.
The approach would be as follows: using as an experimental control group the patients who died without any associated disease (but positive for the virus), they would be compared with the positive ones who also have the disease.
We would represent the results for each disease in two different ways. First, for scientific personnel through a boxplot that would allow at a glance to compare between emperimental groups; and, through a scatter plot, with which we would analyze the linear regression. On the X axis we would have the categorical result of the presence or not of the disease under study, and on the Y axis the difference between the date of death and the date of admission of the patient in number of days.
A simple scientific study using T-student would allow us to objectively and simply obtain information on how the disease may or may not be increasing the probability of death (analyzed on the boxplot), while the scatter plot would allow us to draw a regression line and obtain more precise data on what trend generates the disease.
Additionally, we would make a study of dummy variables to make a more mathematical approximation of how diseases might be affecting the sex of the patient.

