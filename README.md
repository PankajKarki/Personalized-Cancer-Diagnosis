# Personalized-Cancer-Diagnosis
Applying various machine learning classification techniques on a dataset which contains around 3.3K datapoints of Gene ( Gene causing cancer ), Variations ( Variations in the architecture of amino acids or variations in protein-protein interactions ) and TEXT ( Medical Literature which will help in classifying the type of cancer) . Here our task is to classify the given datapoint consisting information of Gene and Variation into one of the 9 cancer classes mentioned in the dataset using medical literature

# Description
A lot has been said during the past several years about how precision medicine and, more concretely, how genetic testing is going to disrupt the way diseases like cancer are treated. Once sequenced, a cancer tumor can have thousands of genetic mutations. But the challenge is distinguishing the mutations that contribute to tumor growth (drivers) from the neutral mutations (passengers). As not all mutations lead to cancer. Due to a mutation in a gene, there is some genetic variation developed in a gene. But the question comes, from which particular mutation this genetic variation happened in a gene. Currently this interpretation of genetic mutations is being done manually which is a very time-consuming task. Based on a gene and a variation in it, a clinical pathologist has to manually review and classify every single genetic mutation based on evidence from text-based clinical literature.

# The workflow is as follows:
1.A molecular pathologist selects a list of genetic variations of interest that he/she want to analyze.

2.The molecular pathologist searches for evidence in the medical literature that somehow are relevant to the genetic variations of interest.

3.Finally, this molecular pathologist spends a huge amount of time analyzing the evidence related to each of the variations to classify them into any one of the 9 different classes. Our goal here is to replace step 3 by a machine learning model. The molecular pathologist will still have to decide which variations are of interest, and also collect the relevant evidence for them. But the last step, which is also the most time consuming, will be fully automated by a machine learning model.

### Our goal here is to replace step 3 by a machine learning model. The molecular pathologist will still have to decide which variations are of interest, and also collect the relevant evidence for them. But the last step, which is also the most time consuming, will be fully automated by a machine learning model.

# Problem Statement
Classify the given genetic variations/mutations based on evidence from text-based clinical literature. In this problem, we need to find the mutation-type given the gene, variation and some text data from published research.

# Source of Data
Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/data Data: Memorial Sloan Kettering Cancer Center (MSKCC)

# Real-world/Business objectives and constraints.
No low-latency requirement. Interpretability is important. Errors can be very costly. Probability of a data-point belonging to each class is needed.

# Getting Started
Start by downloading the project and run " Personalized-Cancer-Diagnosis.ipynb" file in ipython-notebook.

# Prerequisites
You need to have installed following softwares and libraries in your machine before running this project.

1. Python 3: https://www.python.org/downloads/
2. Anaconda: https://www.anaconda.com/download/
3. mlxtend: pip install mlxtend

# Case Study Explanation : 
Objective: Predict the probability of each data-point belonging to each of the nine classes.
<br>
<br>
[ 1 ] We have two files, named as 'training_variants' and 'training_text' which contains the whole dataset.
<br>
[ 2 ] Reading Dataset :- Lets read and save the data point (gene and variation data) in pandas dataframe(data_variants).
<br> Number of data points :  3321
<br> Number of features :  4
<br> Features :  ['ID' 'Gene' 'Variation' 'Class']
<ul>
<li>ID : the id of the row used to link the mutation to the clinical evidence</li>
<li>Gene : the gene where this genetic mutation is located</li>
<li>Variation : the aminoacid change for this mutations</li>
<li>Class : 1-9 the class this genetic mutation has been classified on</li>
</ul>
Lets read and save the data point (text data) in pandas dataframe(data_text).
<br> Number of data points :  3321
<br> Number of features :  2
<br> Features :  ['ID' 'TEXT']
<ul>
<li>ID : the id of the row used to link the mutation to the clinical evidence</li>
<li>TEXT : clinical evidence (text) that human experts/pathologists use to classify the genetic mutations</li>
</ul>
<br>
[ 3 ] Preprocessing of text data:-
<ul>
<li>Stopword removal using nltk library</li>
<li>Merged data_variants, data_text into one dataframe</li>
<li>Null checking using 'result[result.isnull().any(axis=1)]'</li>
<li>Filling the null data 'result.loc[result['TEXT'].isnull(),'TEXT'] = result['Gene'] +' '+result['Variation']'</li>
</ul>
<br>
[ 4 ] Data splitting:- Splitting data into train, test and cross validation (64:20:16)


# Built With
•	ipython-notebook - Python Text Editor

•	sklearn - Machine learning library

•	seaborn, matplotlib.pyplot, - Visualization libraries

•	numpy, scipy- number python library

•	pandas - data handling library

•	mlxtend - used for stacking the models

# Acknowledgments
•	Applied AI Course
