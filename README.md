# Credit Risk Analysis
## Overview
In this analysis, we set out to find a model that would most accurately predict which loan applications were at low or high risk of defaulting.  Using a dataset from LendingClub with over 100,000 rows of loan applications, we quickly realized this was a heavily unbalanced calssification problem due to how the number of "good" loans outweighed the "bad".  

In the results below, you'll see the outcomes of machine learning algorithms such as RandomOverSampling, SMOTE, ClusterCentroids, SMOTEEN, BalancedRandomForestClassifier and EasyEnsembleClassifier which we used to resample the data.  

**Other Tools and Librairies Used:**
- Python
- scikit-learn
- imbalanced-learn


## Results 
We started our analysis by checking the balance of our target values.  As per the image below, you can see the number of low risk applications severely outweighs the high risks.  We the split our data into training and testing sets.  

insert image

### Comparing Resampling Models to Predict Credit Risk 
#### Naive Random Oversampling
First, we used the RandomOverSampler model to add from the miority class into to the training set to equalize the classes.

- Using RandomOverSampler, we recieved an accuracy score of about 64%. 

insert image 

- For the classification report, this model produced a:
  -  precision rate of 1% for the high risk applications
  -  recall rate at 66% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 62% for the low risk applications

insert image 

#### SMOTE Oversampling 
Continuing on with oversampling, we then used the SMOTE model to create new values in the minority class based on their nearest neighbor.  

- The SMOTE model recieved an accuracy score of 65%. 

insert image

- For the classification report, this model produced a:
  -  precision rate of 1% for the high risk applications
  -  recall rate at 61% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 69% for the low risk applications

  insert image

#### ClusterCentroids Undersampling
Next, we decided to change things up and try undersampling as opposed to oversampling.  For this, we started with the ClusterCentroids model that generates synthetic data points that represent clusters of the majority class.  

- this model recieved an accuracy score of 54%. 

insert image

- For the classification report, this model produced a:
  -  precision rate of 1% for the high risk applications
  -  recall rate at 69% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 40% for the low risk applications

### Using SMOTEEN to Predict Credit Risk 
#### SMOTEEN   
We used the SMOTEEN model next which combines over and undersampling.  

- this model recieved an accuracy score of 64%. 

insert image

- For the classification report, this model produced a:
  -  precision rate of 1% for the high risk applications
  -  recall rate at 72% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 57% for the low risk applications

insert image

### Ensemble Classifiers to Predict Credit Risk 
#### Balanced Random Forest
The Balanced Random Forest model works to reduce bias by creating two trees of equal size for the majority and minority classes. 

- this model recieved an accuracy score of 54%. 

insert image

- For the classification report, this model produced a:
  -  precision rate of 3% for the high risk applications
  -  recall rate at 70% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 87% for the low risk applications

insert image

#### EasyEnsemble 
Lastly, we use the Easy Ensemble Classifier model where new examples are created and classified by a set of idividual decisions.  

- this model recieved an accuracy score of 93%. 

insert image

- For the classification report, this model produced a:
  -  precision rate of 9% for the high risk applications
  -  recall rate at 92% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 94% for the low risk applications

insert image

## Summary 
Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.

In our first four models, Naive Random Oversampling, SMOTE, ClusterCentroid and SMOTEEN, we used variations of under and over sampling to balance our data.  These models yeilded accuracy scores within an 11 point margin (54%-65%).  While any higher accuracy rate is best, it wasn't until we started utilizing ensemble classifiers that we saw a clear difference in accuracy, precision and reacall.  

Thus, I reccomend that we use the Easy Ensemble Classifier model moving forward based on it's high accuracy, precision and recall rates in comparison to the others'.  

Easy Ensemble Classifier Stats:

insert image 
insert image
