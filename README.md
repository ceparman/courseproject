# Getting and Cleaning Data Course project
Craig Parman  
2/18/2015  

#Introduction
Using the data from 

[link] https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
 
 with the documentation from: 
 
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 

#Data processing

A summary data set was created.  The data is measurements of motion collected on a cell phone for 30 subjects doing 6 different activities. Several different measurements were collected by the cell phone and then post processed.  The data used for this analysis data is a subset of the full data set, including only the mean and standard deviations of the measurement variable. A full description of the measurement data can be found in the documentation above. 

Subjects are indicated by the subject column ranging from 1-30.
Six activities were performed and are listed in the table below.

1. WALKING
2. WALKING_UPSTAIRS
3. WALKING_DOWNSTAIRS
4. SITTING
5. STANDING
6. LAYING

There are multiple values for measurement for each subject -activity combination.

the data was processed with the script run_analysis.R.  This script also includes comment which detail how the analysis was done.  

#Final output


The final output table - "tall-skinny_summary" contain the mean and standard deviation values for each measurement value organized in a tall skinny table. This table has four columns  "subject"  "activity" "Measure"  "value" 
## Final ata columns
Subject - subject number value 1 to 30
activity - one of the 6 activities listed above
Measure - 146 different values Standard Deviation are designated with a value ending in _sd, means with _mean.
Value - the value of the measure
