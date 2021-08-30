
<img src='https://raw.githubusercontent.com/Milenaafeworki/Bridges-Condition-Classification/master/images/bridges.jpg'>



# Bridges-Classificaiton-Model 

January 2019 marked the release of the Long-Term Bridge Performance (LTBP) Program’s InfoBridge™ web portal, a newly developed website for dissemination and visualization of bridge data, information, and products developed by the LTBP Program. The portal’s main purpose is to leverage the analytical capability of the highway bridge research community, and fulfill the Federal Highway Administration’s (FHWA’s) responsibility to provide transparency and ready access to data collected through Federal research programs.


## Business Problem

Bridge management practices of departments of transportation is looking to assist bridge managers in making consistent and cost-effective decisions related to maintenance and rehabilitation of bridges. The decision making, either at the network level or at the project level, is based on current and future bridge conditions. Therefore, it is essential for a bridge management system to be capable of accurately predicting future bridge conditions to help make an informed decision on when and where to allocate maintenance budgets. 


## Data Understanding

The data pattern underlying the historical bridge inspection records contains useful information in describing the deterioration trends of highway bridge decks, sub-structure and super-structure. Therefore, developing an appropriate algorithm that can identify data patterns buried in history can solve the condition-forecast problem. The data-mining algorithm emphasizes the changing trends of bridge condition ratings along withother factors that may influence the structure-deterioration process.

The analysis uses NBI and climatic data from InfoBridge. The climatic data refer to the annual
numbers (unit in days) of freeze-thaw cycles and snowfalls. The National Aeronautics and Space
Administration (NASA) Modern-Era Retrospective Analysis for Research and Applications,
Version 2 (MERRA-2) program provides the original source of climate data  which is currently available from January 1, 1980 to December 31, 2020.

```
  NBI scale    Condition    Description

        9	Excellent     New condition, no noteworthy deficiencies.
        8	Very good     No repair needed.
        7	Good          Some minor problems, minor maintenance needed.
        6	Satisfactory  Some minor deterioration, major maintenance needed.
        5	Fair          Minor section loss, cracking, spalling, or scouring.
        4	Poor          Advanced section loss, deterioration, spalling or scouring; major rehabilitation needed. 
        3	Seriou        Section loss, deterioration, spalling or scouring seriously affected primary components.
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

## Results

<img src='https://raw.githubusercontent.com/Milenaafeworki/Bridges-Condition-Classification/master/images/poor&fair.jpg'>

<img src='https://raw.githubusercontent.com/Milenaafeworki/Bridges-Condition-Classification/master/images/top20poor.jpg'>

