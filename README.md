# Patent Classifier 
## Abstract 

## Introduction

## Data 
The data is three tab separated variable text files from the USPTO Patent View database. The data sets are relatively large with the largest of the three, the data set containing the claims data, at 40 GB. The next largest data set is the one containing the data about each patent. This data included the title, abstract and date and took up about 6 GB of space. The third and smallest data set contained data the cpc classification info for each patent. The cpc classification file takes up about 4 GB of space. The variance in data sets size are due to both the difference in the number of rows and the ammount of text data in each element. Each of the data sets contained data needed for the patent classification. However, not all of the data from each data set was needed. Only a subset of the data was used in the classification. In addition, many patents have mulitiple claims and cpc classsifications. Thus, to advoid repetition in the tsv file, All of the claims belonging to a single patent were concatenated together. 
## Method 

## Results 

## Conculsion 

## Sources 
