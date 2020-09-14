# Capstone Project 

### Applied Data Science Capstone by IBM/Coursera

## Table of contents
* [Introduction: Business Problem](#introduction)
* [Data](#data)
* [Methodology](#methodology)
* [Analysis](#analysis)
* [Results and Discussion](#results)
* [Conclusion](#conclusion)


## Introduction Business Problem <a name="introduction"></a>



#### Background
The Seattle Police Department (SPD) provides road collisions records since 2004. The records describe the severity of each collision (0 property damage/1 personal injury) with additional information.

Preventing road collisions is a major concern for public authorities. Therefore, it is important to accurately predict whatever a serious accident will occur. It is also important to identify the factors causing serious accidents, as these could be eliminated or mitigated.

#### Problem
This project aims to predict the severity of a collision given other factors, such as the wheatear condition, the road condition, the number of vehicles involved, and the number of persons on the road.

#### Interest
A model predicting the severity of collisions can be used for a warning system. The SPD could issue a warning on road signs when a serious accident is predicted (severity 1, personal injury), to inform the drivers to pay more attention while driving.

## 2. Data <a name="data"></a>

#### Sources

The data used for this study was obtained from the Seattle Department of Transportation.

#### Feature selection

The data used is from Seattle's Collision GIS (Geographic Information System), a computer system used for capturing, storing and displaying data related to positions on Earth's surface. The data is from 2004 to the present and contains various features such as location, the severity of the collision, number of vehicles/cyclists/pedestrians involved, date/time of incident, weather, road conditions and more. There are almost 200,000 collisions in the dataset and 38 features. While some of the features won't be useful or have many missing values, the ones that I will explore in more detail will be:
* Severity Code - this will be the target that we'll compare the features' impact on.
* Severity Description - description of the severity codes.
* X and Y values (coordinates) - are there areas where collisions are more concentrated?
* Address Type - alley, block or intersection of collision.
* Collision Type - 10 types of collisions such as parked car, angles, rear end, pedestrian, etc.
* Person Count - # of people involved in collision.
* Pedestrian Count - # of pedestrians involved in collision.
* Cyclist Count - # of cyclists involved in collision.
* Vehicle count - # of vehicles involved in collision.
* Date/Time - are number of or severity of collisions more likely to occur on certain days or times?
* Junction Type - 7 types describing collision at intersection, mid-block, driveway and whether collision is related to intersection.
* Seattle Collision Code - Seattle codes to describe each collision.
* Seattle Collision Description - description of Seattle collision codes.
* Under Influence - was alcohol or drugs involved?
* Weather - do more collisions occur because of adverse weather?
* Road Conditions - do more collisions occur because of adverse road conditions?
* Light Conditions - do more collisions occur because of adverse light conditions?
* State Collision Code - 84 codes the state uses to descibe each collision.
* State Collision Description - description of state collision codes.
* Hit Parked Car - was a parked car involved in the collision?

In the following section I will use graphs to gain insight into the data, and decide which features will be useful when predicting injuries when these collisions occur.

#### Data Cleaning

The number of null numbers in the database was identified.

<img src=https://github.com/NicolasCalarco/applied_Data_Science/blob/master/recursos/missing%20values.png>

Several other categorical features have a large ratio of missing values: SEVERITYCODE, SPEEDING. 
<img src=https://github.com/NicolasCalarco/applied_Data_Science/blob/master/recursos/missing%20coordenate%20-%20severitycode.png>
<img src=https://github.com/NicolasCalarco/applied_Data_Science/blob/master/recursos/missing%20coordenate%20-%20cars%20velocity.png>

Rows with null values ​​will be removed for analysis-speeding


## 3. Metodology <a name="methodology"></a>

Jupyter Notebooks was used to perform the analysis and all the necessary Python libraries such as Pandas, Numpy, Matplotlib and Seaborn will be imported. The data was mostly categorical, therefore most variables are plotted in graphs to see the correlation between various variables.

The csv file was imported and I prepare the data, I dropped the columns that we do not need from the dataset, that is, columns that have no values or where the values are unknown.

## 4. Analysis <a name="analysis"></a>

We want to know as a first general rule, the incidence between the two types of severity of injuries caused by accidents. For a better representation, the two data sets are plotted.

<img src=https://github.com/NicolasCalarco/applied_Data_Science/blob/master/recursos/collision%20severity.png>

<img src=https://github.com/NicolasCalarco/applied_Data_Science/blob/master/recursos/map%20collisions.png>

In order to see if there is a relationship between the allowed speed and types of accidents, first you have to reflect with which set of types of accident is included in the information and what is its incidence.



