# DA-bellabeat
This is a data analysis case study for Bellabeat smart device with health monitoring capabillities. All the work in this project was done by myself, while the datasets are cited in the Phase 2: Prepare section.

## Basic Analysis 


### Part 1: The Questions

To begin I consider the main questions I need to answer with this data analysis, which are:
  
  * What are some trends in smart device usage?
  * How could these trends apply to Bellabeat customers?
  * How could these trends help influence Bellabeat marketing strategy?

### Part 2: The Data

Dataset I am using: [Public FitBit data on Kaggle](https://www.kaggle.com/datasets/arashnic/fitbit)
 * There are a total of 15 sheets in this dataset
 * The data types are bits, ints, doubles, dates, and booleans.
 * For more details about the other data, refer to the technical analysis section at the bottom.

### Part 3: Choosing tools and cleaning the datasets

For this analysis I chose to use R, because of how much data there is in this dataset.

After importing the data into RStudio and inspecting it, I noticed that the data type for the dates column of the dailyActivity are chars instead of date type, so I got them converted to the right type.

I didn't spot any other problems with the data in this dataset.

### Part 4: Let's Visualize!

  * I'm color grading all of the scatter plots by Total Minutes Asleep to help relate everything to sleep.
  * Note: The Facet Wraps are all by ID, each ID represents a person that consented to having their FitBit data shared.


  * 1: How do the total distance variables relate to the sedentary minutes variables?
    
![TD+SM+TMA](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/42d70936-109f-4609-9e20-042b4963c8cf)
![TD+SM+TMA-FacetWrapID](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/253072f1-d778-4deb-9e41-85f11d38da8f)

  * 2: How do the total distance variables relate to the different Active Minutes variables?
    
##### Very Active Minutes:
![TD+VAM+TMA](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/c40282ea-405e-4de7-84b2-7cb20e1768df)
###### Variations
![TD+VAM+TMA-Filtered](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/9b7231ce-4ec8-4651-9953-c63da6267be1)
![TD+VAM+TMA-FacetWrapID](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/be1e63dd-280f-44a5-bad9-1260d9fb7966)

##### Fairly Active Minutes:
![TD+FAM+TMA](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/a43d7c21-dbe5-4f2b-b90d-416d3de10ca9)
##### Variations
![TD+FAM+TMA-Filtered](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/b2608294-fab6-494c-8f45-65bb7fdf9bf6)
![TD+FAM+TMA-FacetWrapID](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/13c21003-87b0-482a-a1f8-0782d7035689)
##### Lightly Active Minutes:
![TD+LAM+TMA](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/0b519b4f-032b-45a0-80f1-ce6885c76622)
###### Variations
![TD+LAM+TMA-Filtered](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/22a9cbae-de7f-4163-a546-d6a7c9cc9ab7)
![TD+LAM+TMA-FacetWrapID](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/c8bc2a54-06c8-4e34-99e3-7d8d23344a16)

  * 3: How does Distance Traveled relate to Calories burned?
![TD+CB+TMA](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/bc044d5a-6924-4aff-9b5c-e74da9c0d376)
![TD+CB+TMA-FacetWrapID](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/0273f68e-edd4-401a-9fd8-a851aed19466)

### Part 5: What can we do with the insights?
#### Answering the questions from part 1:

  * What are some trends in smart device usage?
In the context of this analysis, the smart device trends seem to be around being able to monitor your health which results in helping you find out problems you may be having, or to keep track of your progress as you work toward an athletic or personal goal. 
  * How could these trends apply to Bellabeat customers?
Bellabeat customers could benefit from using smart devices in this manner to monitor their activity by acheiving their body goals, whether those are to burn more calories, be able to push your body further and harder, or simply to stay in good shape.
  * How could these trends help influence Bellabeat marketing strategy?
By marketing the impact that monitoring almost every aspect of your body has on increasing the speed at which you reach your goals, this product will clearly demonstrate that it saves you time and precious money.


#### Here are the conclusions about my questions:

  * From Visualizations 1, it seems in general, that the more sedentary minutes there are and less minutes people spend asleep, the less the Total Distance traveled is. This indicates that when you don't sleep as much, the more inactive you are. This also indicates that the more sedentary minutes you have, the more inactive you are. For those with health concerns, the more you sleep and the more you less you sit around, the better your health will be.

  * From Visualizations 2, it seems that sleep levels don't impact everyone's active minutes the same. Some people don't sleep very much yet are very active, while some people sleep more but are still less active. In general, it seems that the less someone sleeps the less active they are, but there are a lot more outliers than I thought there would be with these visualizations.

  * From Visualizations 3, it is very clear that the more distance someone travels, they burn more calories.

## More Technical Analysis

### Part 1: The Questions

To begin I consider the main questions I need to answer with this data analysis, which are:
  
  * What are some trends in smart device usage?
  * How could these trends apply to Bellabeat customers?
  * How could these trends help influence Bellabeat marketing strategy?


### Part 2: The Data

Dataset I am using: [Public FitBit data on Kaggle](https://www.kaggle.com/datasets/arashnic/fitbit)

This dataset is fitbit data from 33 users who consented to giving out this data publicly.

Dataset composition:
  * This dataset is made up of 17 different spreadsheets and one combined spreadsheet, the names of each sheet are as follow:
  * The data types in this dataset are bits, booleans, dates, int, and doubles.
     * dailyActivity_merged
       * This sheet is comprised of 15 columns and 940 rows, and is a general combination of all data from the other sheets. I am only going to be using this sheet and the sleepDay_merged sheet for my analysis, because they provide a good picture of all the data collected together.
       * Column names: Id, ActivityDate, Totalsteps, TotalDistance, TrackerDistance, LoggedActivitiesDistance, VeryActiveDistance, ModeratelyActiveDistance, LightActiveDistance, SedentaryActiveDistance, VeryActiveMinutes, FairlyActiveMinutes, LightlyActiveMinutes, SedentaryMinutes, and Calories
     * sleepDay_merged
       * This sheet has 5 columns, with 413 rows. It contains how many minutes each of the participants slept and spent in bed each day during the data collection. This sheet only has sleep data from 24 users instead of the total 33.
       * Column names: Id, SleepDay, TotalSleepRecords, TotalMinutesAsleep, TotalTimeInBed
     * dailyCalories_merged 
     * dailyIntensities_merged
     * dailySteps_merged
     * heartrade_seconds_merged
     * hourlyCalories_merged
     * hourlyIntensities_merged
     * hourlySteps_merged
     * minuteCaloriesNarrow_merged
     * minuteCaloriesWide_merged
     * minuteIntensitiesNarrow_merged
     * minuteIntensitiesWide_merged
     * minuteMETsNarrow_merged
     * minuteSleep_merged
     * minuteStepsNarrow_merged
     * minuteStepsWide_merged
     * weightLogInfo_merged

### Part 3: Choosing tools and cleaning the datasets
For this analysis I chose to use R, because of how much data there is in this dataset.

After importing and inspecting the data, I noticed that the data type for the dates column of the dailyActivity is a char instead of date type, so I got them converted to the right type.

I didn't spot any other problems with the data in this dataset.

### Part 4: Let's Visaulize!

  * I'm color grading all of the scatter plots by Total Minutes Asleep to help relate distances traveled to sleep.
  * Note: The Facet Wraps are all by ID, each ID represents a person that consented to having their FitBit data shared.
  * 1: How do the total distance variables relate to the sedentary minutes variables?
    
![TD+SM+TMA](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/42d70936-109f-4609-9e20-042b4963c8cf)
![TD+SM+TMA-FacetWrapID](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/253072f1-d778-4deb-9e41-85f11d38da8f)

  * 2: How do the total distance variables relate to the different Active Minutes variables?
    
##### Very Active Minutes:
![TD+VAM+TMA](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/c40282ea-405e-4de7-84b2-7cb20e1768df)
###### Variations
![TD+VAM+TMA-Filtered](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/9b7231ce-4ec8-4651-9953-c63da6267be1)
![TD+VAM+TMA-FacetWrapID](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/be1e63dd-280f-44a5-bad9-1260d9fb7966)

##### Fairly Active Minutes:
![TD+FAM+TMA](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/a43d7c21-dbe5-4f2b-b90d-416d3de10ca9)
##### Variations
![TD+FAM+TMA-Filtered](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/b2608294-fab6-494c-8f45-65bb7fdf9bf6)
![TD+FAM+TMA-FacetWrapID](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/13c21003-87b0-482a-a1f8-0782d7035689)
##### Lightly Active Minutes:
![TD+LAM+TMA](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/0b519b4f-032b-45a0-80f1-ce6885c76622)
###### Variations
![TD+LAM+TMA-Filtered](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/22a9cbae-de7f-4163-a546-d6a7c9cc9ab7)
![TD+LAM+TMA-FacetWrapID](https://github.com/Oreo2274/DA-bellabeat/assets/46305910/c8bc2a54-06c8-4e34-99e3-7d8d23344a16)


### Part 5: What can we do with the insights?
#### Answering the questions from part 1:

  * What are some trends in smart device usage?
In the context of this analysis, the smart device trends seem to be around being able to monitor your health which results in helping you find out problems you may be having, or to keep track of your progress as you work toward an athletic or personal goal. 
  * How could these trends apply to Bellabeat customers?
Bellabeat customers could benefit from using smart devices in this manner to monitor their activity by acheiving their body goals, whether those are to burn more calories, be able to push your body further and harder, or simply to stay in good shape.
  * How could these trends help influence Bellabeat marketing strategy?
By marketing the impact that monitoring almost every aspect of your body has on increasing the speed at which you reach your goals, this product will clearly demonstrate that it saves you time and precious money.


#### Here are the conclusions about my questions:

  * From Visualizations 1, it seems in general, that the more sedentary minutes there are and less minutes people spend asleep, the less the Total Distance traveled is. This indicates that when you don't sleep as much, the more inactive you are. This also indicates that the more sedentary minutes you have, the more inactive you are. For those with health concerns, the more you sleep and the more you less you sit around, the better your health will be.

  * From Visualizations 2, it seems that sleep levels don't impact everyone's active minutes the same. Some people don't sleep very much yet are very active, while some people sleep more but are still less active. In general, it seems that the less someone sleeps the less active they are, but there are a lot more outliers than I thought there would be with these visualizations.

  * From Visualizations 3, it is very clear that the more distance someone travels, they burn more calories.

