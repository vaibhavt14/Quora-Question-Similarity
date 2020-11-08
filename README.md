# Quora-Question-Similarity: Project Overview 
* It is a binary classification problem, for a given pair of questions we need to predict if they are duplicate or not.
* Identify which questions asked on Quora are duplicates of questions that have already been asked.
* This could be useful to instantly provide answers to questions that have already been answered.
* We are tasked with predicting whether a pair of questions are duplicates or not.  
* Optimized Logistic Regressor,Linear SVM, and XGBoost to reach the best model. 
* Performance metrics: log-loss


## Code and Resources Used 
**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn, nltk,plotly,sqlite

## Dataset
*	id:Unique Id
*	qid1:Unique id for each question 1
*	qid2:Unique id for each question 2
*	question1,question2:These are the text of questions
*	is_duplicate:Binary variable i.e is question1 and question2 duplicate of one another(0->No duplicate,1->duplicate)

## Data Cleaning
After understanding business requirements, I needed to clean it up so that it was usable for our model. I made the following changes and created the following variables:

*	Cleaned the duplicates rows 
*	Checking for null values 
*	Preprocessed the text such as removing html tags,punctuations,stemming,stopwords
*	Advanced feature extraction (Fuzzy Features)
*	Made a new column by using given features
* Analyses of extracted features
* Implemented TF-IDF weighted average
* Applied T-SNE 
  

## EDA
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables. 

![alt text](https://github.com/vaibhavt14/Quora-Question-Similarity/blob/main/class_distribution.png "Class distribution of target variable")
![alt text](https://github.com/vaibhavt14/Quora-Question-Similarity/blob/main/questions.png "Distribution of unique and repeated")
![alt text](https://github.com/vaibhavt14/Quora-Question-Similarity/blob/main/questions_occurence.png "question appeareance counts")

## Model Building 

I split the random data into train and tests sets with a test size of 30%.Build random model to identify worst case log loss  

I tried three different models with hyperparameter tuning  and evaluated them using log-loss compare the log-loss for each train,test 


## Model performance
The XG Boost far outperformed the other approaches on the test set. 
*	**Logistic Regression** : log-loss = 0.52
*	**Linear SVM**: log-loss = 0.489
*	**XG Boost**: log-loss = 0.357




