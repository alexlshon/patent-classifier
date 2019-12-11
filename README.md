# Patent Classifier 

Patent classification is a challenging task due to large number of possible subject matters that a patent can be classified into. This challenge is compounded by the high level of technical vocabulary and the large size of the patent document which leads to high dimensional predictor vectors. Using natural language processing and word vectorization, A model is to be generated that can correctly classify patents into their correct patent classification. The dataset of patents used is about 50 GB which adds considerable challenges in modeling due to its size. Challenges that are met using apache spark, an analytical framework that specializes in computing big data. Using apache spark, patents split into training and testing groups. Naive Bayes and cosine similarity models are fitted on the training data and transformed on the testing data. The models are then scored using accuracy. The scores from these relatively simple models are then compared to scores on more complex BERT model done in the literature.  

## Introduction And Background  
   Patents classification by computer algorithm is a problem that has confounded researchers and business for decades. The only easy part about patent classification is collecting the data. Most data on patents are open and made freely available to the public by governments. Nearly the entire digital database of the USPTO is accessable to the public through api or direct downloads of the archived databases. The data gathered from the USPTO is also generally clean, structured and formatted in tsv, xml or json. Access to patent data is open and free for patents from the European Union, United Kingdom and Japan. For this project, zipped tsv files containing the datasets were downloaded from PatentView, a service provided by the USPTO to support patent research. 

### Patent Classification 
   Any effective method of patent classification by technical subject matter must have and balance the following three properties.
 - Cover the entire range of possible technical subject matter 
 - Have enought granularity to distinguish related patents
 - Yet not too much granularity such that it is no longer an useful abstraction 
 
    A patent classification system that maximizes granularity simiply gives each unique patent its own unique classification. One that minimizes granularity simiply classifies all the patents into one subject matter. Since the number of possible subject matters is extreamly large, neither of these systems are useful abstractions. A more useful system would have a small number of classes. The most useful system would recursively chain together multiple medium granularity classification systems in a hierarchical manner. The number of recursions will be dependant on the level of granularity one wants to reach. A simple classification will require one or two recursions while an advanced classification will need alteast a few. Lets say we want to classify patents into a thousand categories. Instead of trying the classifiy the patents into a thousand different categories at once, we classify only 10 categories with each category classified into 10 sub-categories. Each sub-category is then classified further into 10 sub-sub-categories. Using the recursive method to classify yeilds an hierarchical classification system. Such Hierarchical classification system can be modeled as a Directed Acylic Graph, which is also known as a tree data structure. Many classification systems are structured as hierarchical classification systems. If you are familar with the Dewey Decimal system or the Library of Congress Classification system for classifing books then you are already familar with hierarchical classification systems. All patent classification systems are heriarchical, what differs between patent systems in patent offices of different nations is the categories used for each level. Since 2013, the patent offices of the US and EU have harmonized their patent classification systems called the CPC.

    The current system of patent classification is the Cooperative Patent Classification CPC) for the United States Patent and Trademark Office (USPTO) and the European Patent Office (EPO). A series of symbols are used to represent the category. When the series is read left to right, The first is symbol represents the highest level of categorization which each symbol to the left representing one level down in categorization. The schema with their represenative symbols for the CPC hierarchies are given below. 
- Section (one letter A to H and also Y)
    - Class (two digits)
        - Subclass (one letter)
            - Group (one to three digits)
                - Main group and subgroups (at least two digits)


For example, A recent patent from Google titled *Neural Network Processor*, patent number US20160342891A1, has the primary CPC classification as G06N3/08. Each of the subject matter classifications, for this patent, by level are the following 
- Section G (Physics)
    - Class G06 (Computing; Calculating; Counting)
        - Subclass G06N (Computer Systems Based on Specific Computational Models)
            - Group G06N3 (Computer Systems Based on Biological Models)
                - Main group and subgroups G06N3/08 (Learning Methods)

## Data 
   The data is three tab separated variable text files from the USPTO Patent View database. The data sets are relatively large with the largest of the three, the data set containing the claims data, at 40 GB. The next largest data set is the one containing the data about each patent. This data included the title, abstract and date and took up about 6 GB of space. The third and smallest data set contained data the cpc classification info for each patent. The cpc classification file takes up about 4 GB of space. The variance in data sets size are due to both the difference in the number of rows and the ammount of text data in each element. Each of the data sets contained data needed for the patent classification. However, not all of the data from each data set was needed. Only a subset of the data was used in the classification. In addition, many patents have mulitiple claims and cpc classsifications. Thus, to advoid repetition in the tsv file, All of the claims belonging to a single patent were concatenated together. 
   
## Method 

## Results 

## Conculsion 

## Sources 
