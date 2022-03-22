# cancer-prediction-from-Gene-Data

## Problem Definitions:
 
once a patient seems to have some problem, the first thing the doctors does is they take the cancer tumor from the patient,and they do genetic sequencing on it which gives the Gene.These genes mutate. Mutations on genes are basically small changes in the gene, which can corrupt the genetic code.A mutated Gene might casue cancer. There is a lot of mutual effort by a clinical pathologist who actually take a list of genetic variations that are of interest that they think that we should start analyzing for potential signals of cancer and search for evidance in the Medical literature,they spend huge amount of time on this.The whole purpose of machine learning in this context for this problem is to speed up analyzing this research that has been collected to determine which of the classes it belongs to.
 
 
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

![](images/Distribution%20of%20Y%20in%20train%20data.jpg)


