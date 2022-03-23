# cancer-prediction-from-Gene-Data

## Problem Definitions:
 
once a patient seems to have some problem, the first thing the doctors does is they take the cancer tumor from the patient,and they do genetic sequencing on it which gives the Gene.These genes mutate. Mutations on genes are basically small changes in the gene, which can corrupt the genetic code.A mutated Gene might casue cancer. There is a lot of mutual effort by a clinical pathologist who actually take a list of genetic variations that are of interest that they think that we should start analyzing for potential signals of cancer and search for evidance in the Medical literature,they spend huge amount of time on this.The whole purpose of machine learning in this context for this problem is to speed up analyzing this research that has been collected to determine which of the classes it belongs to.

## Central Dogma of molecular biology


![](Images/Central%20Dogma.png)

Nucleotides from the DNA are transcribed. They're complementary forms on RNA, which are then read as codons or groups of three to code for specific amino acids and a larger protein.Now, if you mutate one of the nucleotides on DNA that ultimately lead to abnormal protein production which may lead to cancer. 


 
 
 ## Problem Statement: 
 
classify a genetic variation or a mutation, based on evidence from text placed clinical research.
 
So we want to classify given a gene and a variation and some text corresponding to this gene and variation,this text is basically all the literature survey or all the research which has been done on this gene and variation that the domain expert has collected.We want to use this text to determine which of the classes does this gene and variation fall into. 

## Business objectives and constraints.

 - No low-latency requirement. <br/>
 - Interpretability is important. <br/>
 - Errors can be very costly.<br/>
 - Probability of a data-point belonging to each class is needed.<br/>
  
## Data Overview:

Data sourcce:Memorial Sloan Kettering Cancer Center (MSKCC)

We have two data files: one conatins the information about the genetic mutations and the other contains the clinical evidence (text) that human experts/pathologists use to classify the genetic mutations.Both these data files have a common column called ID.

Data file's information: <br/>
variants (ID , Gene, Variations, Class) <br/>
text (ID, Text) <br/>

## Mapping the real-world problem to an ML problem

### Type of Machine Learning Problem

There are nine different classes a genetic mutation can be classified into => Multi Class Classification Problem

### Performance Metric

- Multi Class log-loss: To penalise the errors in class probabilities.
- Confusion matrix

## Objective
Predict the probability of each data-point belonging to each of the nine classes.

## Train,CV and Test Datasets

split the data into three parts train,cross validation and test with 64%,16%,20% of data respectively.


## Exploratory data analysis


<p float="left">
  <img src="Images/distribution_of_Y_in_TraindatA.png" width="320" />
  <img src="Images/distribution_of_Y_in_Testdata.png" width="320" /> 
  <img src="Images/distribution_of_Y_CV_data.png" width="320" />
</p>





#### Takeaway from the above visualizations:
We are operating on multi class classification problem and the data is imbalanced.<br/>
The Train,Test and Cross Validation data have similar distribution of the class label Y.<br/>


### Confusion matrix 

![](Images/confusion_matrix.jpg)


### Precision Matrix


![](Images/Precision_Matrix.jpg)


### Recall_matrix


![](Images/recall_matrix.jpg)


## Univariate analysis on Gene Feature 


<p float="left">
  <img src="Images/PDF_Gene_Feature%20.jpg" width="400" />
  <img src="Images/CDF_Gene-Feature.jpg" width="400" /> 
</p>

#### Best Hyperparameter

![](Images/Best_HyperParameter_Gene_feature%20.jpg)

#### Conclusion:

The Logloss for the Gene Feature is less than the Random model and the Gene Feature is stable because the CV and Test erroes are almost near to the Train error,there is significant difference between them.


## Univariate analysis on Gene Variation

<p float="left">
  <img src="Images/Histogram_Gene_Variation.jpg" width="400" />
  <img src="Images/CDF_Gene%20Variation.jpg" width="400" /> 
</p>

#### Best Hyperparameter for Gene Variation

![](Images/Best_hyperparameter_Gene_Vatiation.jpg)

#### Conclusion:

Even Gene Variation feature is important because the log less is less when compared to Random model but Gene Variation is less stable becuase when compared to Gene feature.



## Univariate analysis on Text Feature 


#### Best Hyperparameter for  Text Feature 

![](Images/Best_HyperParameter_Text.jpg)

#### Conclusion:

The text feature is the most important feature because the log loss is less for all the train,Test and CV data.


# Machine learning Models

- K-Nearest Neighbors
- Logistic Regression with ClassBalancing
- Logistic Regression without Class Balancing 
- Support Vector Machines With Class Balancing 
- Random Forest with one hot encoding 
- Random Forest with response coding 


## Below is a little snip of the logistic regression model confusion matrix and the best hyperparameters.

![](Images/confusion_matrix_logistic_regression.jpg)
![](Images/precision_matrix_logistic_regression.jpg)
![](Images/Recall_Matrix_logisticRegression.jpg)



## Analysis summary

![](Images/Final_Results.jpg)















