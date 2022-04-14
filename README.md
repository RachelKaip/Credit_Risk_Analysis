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

![splittingvalues](https://user-images.githubusercontent.com/94569240/163395313-98b72520-73a4-4a2e-a729-4c655b5cef7f.PNG)

### Comparing Resampling Models to Predict Credit Risk 
#### Naive Random Oversampling
First, we used the RandomOverSampler model to add from the miority class into to the training set to equalize the classes.

- Using RandomOverSampler, we recieved an accuracy score of about 64%. 

![randomaccuracyscore](https://user-images.githubusercontent.com/94569240/163395364-dd3b27d7-38cf-4b66-8728-6c459110f76f.PNG)

- For the classification report, this model produced a:
  -  precision rate of 1% for the high risk applications
  -  recall rate at 66% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 62% for the low risk applications

![Randomcm](https://user-images.githubusercontent.com/94569240/163395399-dd5ff2c4-53be-4f61-b3ef-6c336495ce49.PNG)

![randomclassification](https://user-images.githubusercontent.com/94569240/163395420-d8f28edc-d48e-40c7-a63c-c043d2bea7c2.PNG)


#### SMOTE Oversampling 
Continuing on with oversampling, we then used the SMOTE model to create new values in the minority class based on their nearest neighbor.  

- The SMOTE model recieved an accuracy score of 65%. 

![smoteaccuracy](https://user-images.githubusercontent.com/94569240/163395458-bbe68d8d-b530-49a7-847a-b18a0baaa02d.PNG)

- For the classification report, this model produced a:
  -  precision rate of 1% for the high risk applications
  -  recall rate at 61% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 69% for the low risk applications

 ![smotecm](https://user-images.githubusercontent.com/94569240/163395485-bb7c4c92-c2e6-4bed-9a45-29a37f7ad041.PNG)

![smoteclassification](https://user-images.githubusercontent.com/94569240/163395498-ad20086d-e9f9-4e0e-b4bd-58e798f6c0fa.PNG)

#### ClusterCentroids Undersampling
Next, we decided to change things up and try undersampling as opposed to oversampling.  For this, we started with the ClusterCentroids model that generates synthetic data points that represent clusters of the majority class.  

- this model recieved an accuracy score of 54%. 


- For the classification report, this model produced a:
  -  precision rate of 1% for the high risk applications
  -  recall rate at 69% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 40% for the low risk applications

### Using SMOTEEN to Predict Credit Risk 
#### SMOTEEN   
We used the SMOTEEN model next which combines over and undersampling.  

- this model recieved an accuracy score of 64%. 

![smoteenaccuracy](https://user-images.githubusercontent.com/94569240/163395884-b76e56ef-af0e-4991-9248-add367d82374.PNG)

- For the classification report, this model produced a:
  -  precision rate of 1% for the high risk applications
  -  recall rate at 72% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 57% for the low risk applications

![smoteenclassification](https://user-images.githubusercontent.com/94569240/163395929-5b51a1e3-9ad8-4f21-bd48-a13fec79d18d.PNG)

### Ensemble Classifiers to Predict Credit Risk 
#### Balanced Random Forest
The Balanced Random Forest model works to reduce bias by creating two trees of equal size for the majority and minority classes. 

- this model recieved an accuracy score of 54%. 

![forestaccuracy](https://user-images.githubusercontent.com/94569240/163395977-b4fcc4aa-8be2-4cd5-b79e-d998df99b8c2.PNG)

- For the classification report, this model produced a:
  -  precision rate of 3% for the high risk applications
  -  recall rate at 70% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 87% for the low risk applications

![forestclassificationanndcm](https://user-images.githubusercontent.com/94569240/163396004-6b2114e3-2475-47eb-9b09-d9063f165955.PNG)

#### EasyEnsemble 
Lastly, we use the Easy Ensemble Classifier model where new examples are created and classified by a set of idividual decisions.  

- this model recieved an accuracy score of 93%. 

![EEaccuracy](https://user-images.githubusercontent.com/94569240/163396032-558d9f3a-4ea5-4c2d-a9c5-3ef940be4dbf.PNG)

- For the classification report, this model produced a:
  -  precision rate of 9% for the high risk applications
  -  recall rate at 92% for the high risk applications
  -  precision rate of 100% for the low risk applications
  -  recall rate at 94% for the low risk applications
  
![EEclassification](https://user-images.githubusercontent.com/94569240/163396046-2775d75a-d22e-4178-96da-c61246d14c82.PNG)


## Summary 
Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.

In our first four models, Naive Random Oversampling, SMOTE, ClusterCentroid and SMOTEEN, we used variations of under and over sampling to balance our data.  These models yeilded accuracy scores within an 11 point margin (54%-65%).  While any higher accuracy rate is best, it wasn't until we started utilizing ensemble classifiers that we saw a clear difference in accuracy, precision and reacall.  

Thus, I reccomend that we use the Easy Ensemble Classifier model moving forward based on it's high accuracy, precision and recall rates in comparison to the others'.  

Easy Ensemble Classifier Stats:

![EEaccuracy](https://user-images.githubusercontent.com/94569240/163396084-6e9c3839-c71e-435a-8adf-bf958e204e8b.PNG)

![EEclassification](https://user-images.githubusercontent.com/94569240/163396101-bedff023-0997-44f6-bc68-965b97803a2b.PNG)


