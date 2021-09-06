
<img src='https://raw.githubusercontent.com/Milenaafeworki/Bridges-Condition-Classification/master/images/bridges.jpg'>



# Bridges-Classificaiton-Model 

January 2019 marked the release of the Long-Term Bridge Performance (LTBP) Program’s InfoBridge™ web portal, a newly developed website for dissemination and visualization of bridge data, information, and products developed by the LTBP Program. The portal’s main purpose is to leverage the analytical capability of the highway bridge research community, and fulfill the Federal Highway Administration’s (FHWA’s) responsibility to provide transparency and ready access to data collected through Federal research programs.


## Business Problem

Bridge management practices of departments of transportation is looking to assist bridge managers in making consistent and cost-effective decisions related to maintenance and rehabilitation of bridges. The decision making, either at the network level or at the project level, is based on current and future bridge conditions. Therefore, it is essential for a bridge management system to be capable of accurately predicting future bridge conditions to help make an informed decision on when and where to allocate maintenance budgets. 


## Data Understanding

The data pattern underlying the historical bridge inspection records contains useful information in describing the deterioration trends of highway bridge decks, sub-structure and super-structure. Therefore, developing an appropriate algorithm that can identify data patterns buried in history can solve the condition-forecast problem. The data-mining algorithm emphasizes the changing trends of bridge condition ratings along withother factors that may influence the structure-deterioration process.

The analysis uses NBI and climatic data from InfoBridge. The climatic data refer to the annual numbers (unit in days) of freeze-thaw cycles and snowfalls. The National Aeronautics and Space Administration (NASA) Modern-Era Retrospective Analysis for Research and Applications,
Version 2 (MERRA-2) program provides the original source of climate data  which is currently available from January 1, 1980 to December 31, 2020.

```
  NBI scale    Condition    Description

        9	Excellent     New condition, no noteworthy deficiencies.
        8	Very good     No repair needed.
        7	Good          Some minor problems, minor maintenance needed.
        6	Satisfactory  Some minor deterioration, major maintenance needed.
        5	Fair          Minor section loss, cracking, spalling, or scouring.
        4	Poor          Advanced section loss, deterioration, spalling or scouring; major rehabilitation needed. 
        3	Serious       Section loss, deterioration, spalling or scouring seriously affected primary components.
        2	Critical      Advanced deterioration of primary structural elements; bridge closed. 
        1	Imminent      Major deterioration or loss of section; bridge may be closed to traffic.
               failure
        0	Failed        Out of service and beyond corrective action.

```

## Methods

This project follows the OSEMN process of data science inquiry. 

- Obtain
- Scrub
- Explore
- Modeling (KNN, RandomForest, XGBoost)
- Interpret

## Process

Modeling involved iterating through parameters of the following model types with GridSearchCV and SMOTE:

- K-Nearest Neighbors - KNNClassifier

- Random Forest - RandomForestClassifier

- XGBoost - XGBClassifier

## Results

Of the 7,295 bridges in the state of West Virginia,  21% percent, are classified as structurally deficient. This means one of the key elements is in poor or critical condition.
The second highest “poor condition’  rating state is Iowa with 19% of its bridges being in poor condition and 50% fair condition. 


<img src='https://raw.githubusercontent.com/Milenaafeworki/Bridges-Condition-Classification/master/images/poor%26fair.png'>

Another important feature in the our dataset was the freeze and thaw cycle. Freeze-thaw occurs when water continually seeps into cracks, freezes and expands, eventually breaking the rock apart. Now this feature is most significant in areas affected by snow or very low temperature. Although High freeze-thaw cycle of these states don’t necessarily mean poor condition of bridge, majority of them are highly affected by this factor. 



<img src='https://raw.githubusercontent.com/Milenaafeworki/Bridges-Condition-Classification/master/images/freeze_thaw.png'>

We also explore the States which have the majority of  those critical condition bridges. The Eastern side of the Country consists  of a higher percentage of those poor conditioned structures and as we take a closer look at the heatmap around the zones with the color Red, you can further distinguish that those were some of the top rated states with poor condition that we noted in our previous slide. States locator on blue or green show an average of number of Good and Fair conditions.


<img src='https://raw.githubusercontent.com/Milenaafeworki/Bridges-Condition-Classification/master/images/US_map.png'>

<img src='https://raw.githubusercontent.com/Milenaafeworki/Bridges-Condition-Classification/master/images/States_poor_condition.png'>



## Conclusions and Recommendation


Over all the RandomForest model was able to deliver the best possible alternative algorithm for the Bridge condition calssification. Moreover, class imbalance affected the performance of the models greatly and as a result, the instances belonging to the minority group were consistently misclassified more often than those belonging to the majority group.

**Random forest:** 

   1. Baseline model
    
    Good  (79%)     
    Fair  (76%)   
    Poor  (34%) 
    
    
   2. Gridsearch CV
    
     Good  (66%)     
    Fair   (77%)   
    Poor  (45%) 
    
   3. SMOTE
    
     Good  (77%)     
    Fair   (73%)   
    Poor  (41%) 


 Given more time and with some more tunning it may be able to increase its performance.
 
 ## Further Study
 
- With limited resources to properly maintain and upgrade transportation infrastructure, bridges often end up exceeding their expected
service lifespan and so I would be interested in 
-  investigating if past failures help identify vulnerable bridges to extreme events

- Explore how model would be able to adjust to the process of load rating,  measures of bridge live load capacity, to assess the adequacy of individual structures.


-  Evaluating how wind factors affect the condition of long span bridge could be targeted to showcase its impact.

- Last but not least, incorporating  the above mentioned features and expanding number of parameters used for Classification algorithms to deliver a model much more sophisticated and Robust would be ideal. 

```
├── images
├── Bridge data.ipynb
├── Bridge modeling.ipynb
├── Visualizations.ipynb
├── README.md
├── bridge_data_cleaned1.csv
├── bridge_data_cleaned2.csv
└── bridge_data_cleaned3.csv

``` 
 
 
 

