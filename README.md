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

In order to see if there is a relationship between the permitted speed and types of accidents, we will first reflect on which set of accident types we have in the information and what their incidence is.

At a General level in the last 16 years.

<img src=https://github.com/NicolasCalarco/applied_Data_Science/blob/master/recursos/collisions%type.png>

And at the level of high speed accidents.

<img src=https://github.com/NicolasCalarco/applied_Data_Science/blob/master/recursos/map%20collisions%20velocity.png>

the distribution of the severity of the accidents is observed

<img src=https://github.com/NicolasCalarco/applied_Data_Science/blob/master/recursos/type%20severity%20collision%20speeding.png>

What is interesting from the data obtained is that most accidents did not occur at intersections.

<img src=https://github.com/NicolasCalarco/applied_Data_Science/blob/master/recursos/junction%20type-%20speeding.png>
<img src=https://github.com/NicolasCalarco/applied_Data_Science/blob/master/recursos/addr%20type%20car%20velocity.png>

## Result and Discussion <a name="results"></a>

After conducting the first quick analysis on the data set that we obtained from a sample of accidents in Seattle, it is detailed.

* There are many more collisions that involve only property damage versus injuries.
* Collisions involving injuries tend to occur in and around the city center and major roads, while collisions without injuries are evenly distributed.
* Collisions occur more frequently in blocks than in intersections, very low accident rate in others.
* Most types of collisions are with parked cars. Rear angles and collisions are also common.
* The most frequent number of people involved in collisions is 2.
* Almost no pedestrians or bicyclists are involved in accidents.
* Most collisions involve 2 vehicles.
* Although the number of collisions has fluctuated over the past 16 years, it appears to be trending downward. The recession between 2007-2009 and the growth that followed may have had an impact.
* The number of collisions tends to increase slightly in October and decrease slightly in February.
* The number of collisions tends to go up slightly on Fridays and down slightly on Sundays.
* Most collisions do not involve alcohol or drugs.
* Most collisions occur when the weather is clear, the roads are dry, and it is daytime.
* The "parked car hit" function contradicts the "collision type" function.
* Speeding collisions occur mostly in the middle of the street and not at intersections.

## Conclusion <a name="conclusion"></a>

The data is consistent with each other. Many of the accidents occur under ideal driving conditions. This allows me to give my first opinion that the reasons for the accidents are due to carelessness or poor traffic infrastructure.


**As the first improvement proposal is to limit the maximum speeds in the central streets, since this would drastically reduce collisions.**

Seattle appears to be making progress toward its Vision Zero plan, but it has a long way to go. Some of the most relevant characteristics for predicting the severity of a collision can be the location, the type of direction and the type of collision. Additionally, since most days in Seattle are marked with cloudy skies, good weather and dry conditions can also be good characteristics for predicting the severity of the collision.



