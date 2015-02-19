# CodeBook
Craig Parman  
2/18/2015  


Code book for "tall_skiny_summary.txt"

#summary

This data table was created from the UCI HAR data set.  See the readme for download instructions and through description of the raw data.

The data in tall_skiny_summary.txt consists of the mean and standard deviation for all values of the test and training data sets.  Only column that we results of means and standard deviation were used . *(Yeah, that makes no sense, but that was what the instructions said)*  All proicessing steps are in run_analysis.R

#columns
There are 4 columns in the final table.



```r
t<-read.table("tall_skiny_summary.txt",header=TRUE)
print(names(t))
```

```
## [1] "subject"  "activity" "Measure"  "value"
```

#Variables

##Subject

Meaning: Number assigned to test subject.

Values:  1 to 30, 876 observations for each.

##Activity
Meaning: Type of activity during data collection

Values:  6 values 
1. WALKING
2. WALKING_UPSTAIRS
3. WALKING_DOWNSTAIRS
4. SITTING
5. STANDING
6. LAYING

##Measure
Meaning:  The measurement and the type of summary statistic either mean or standard deviation. All values are in the form [raw measure].[initial summary]_statistic, where statistic is eith mean or std.

Value: 1 of the 146 values listed.

```r
print(names(table(t$Measure)))
```

```
##   [1] "angle.X.gravityMean._mean"                
##   [2] "angle.X.gravityMean._sd"                  
##   [3] "angle.Y.gravityMean._mean"                
##   [4] "angle.Y.gravityMean._sd"                  
##   [5] "angle.Z.gravityMean._mean"                
##   [6] "angle.Z.gravityMean._sd"                  
##   [7] "angle.tBodyAccJerkMean..gravityMean._mean"
##   [8] "angle.tBodyAccJerkMean..gravityMean._sd"  
##   [9] "angle.tBodyAccMean.gravity._mean"         
##  [10] "angle.tBodyAccMean.gravity._sd"           
##  [11] "angle.tBodyGyroJerkMean.gravityMean._mean"
##  [12] "angle.tBodyGyroJerkMean.gravityMean._sd"  
##  [13] "angle.tBodyGyroMean.gravityMean._mean"    
##  [14] "angle.tBodyGyroMean.gravityMean._sd"      
##  [15] "fBodyAcc.mean...X_mean"                   
##  [16] "fBodyAcc.mean...X_sd"                     
##  [17] "fBodyAcc.mean...Y_mean"                   
##  [18] "fBodyAcc.mean...Y_sd"                     
##  [19] "fBodyAcc.mean...Z_mean"                   
##  [20] "fBodyAcc.mean...Z_sd"                     
##  [21] "fBodyAcc.std...X_mean"                    
##  [22] "fBodyAcc.std...X_sd"                      
##  [23] "fBodyAcc.std...Y_mean"                    
##  [24] "fBodyAcc.std...Y_sd"                      
##  [25] "fBodyAcc.std...Z_mean"                    
##  [26] "fBodyAcc.std...Z_sd"                      
##  [27] "fBodyAccJerk.mean...X_mean"               
##  [28] "fBodyAccJerk.mean...X_sd"                 
##  [29] "fBodyAccJerk.mean...Y_mean"               
##  [30] "fBodyAccJerk.mean...Y_sd"                 
##  [31] "fBodyAccJerk.mean...Z_mean"               
##  [32] "fBodyAccJerk.mean...Z_sd"                 
##  [33] "fBodyAccJerk.std...X_mean"                
##  [34] "fBodyAccJerk.std...X_sd"                  
##  [35] "fBodyAccJerk.std...Y_mean"                
##  [36] "fBodyAccJerk.std...Y_sd"                  
##  [37] "fBodyAccJerk.std...Z_mean"                
##  [38] "fBodyAccJerk.std...Z_sd"                  
##  [39] "fBodyAccMag.mean.._mean"                  
##  [40] "fBodyAccMag.mean.._sd"                    
##  [41] "fBodyAccMag.std.._mean"                   
##  [42] "fBodyAccMag.std.._sd"                     
##  [43] "fBodyBodyAccJerkMag.mean.._mean"          
##  [44] "fBodyBodyAccJerkMag.mean.._sd"            
##  [45] "fBodyBodyAccJerkMag.std.._mean"           
##  [46] "fBodyBodyAccJerkMag.std.._sd"             
##  [47] "fBodyBodyGyroJerkMag.mean.._mean"         
##  [48] "fBodyBodyGyroJerkMag.mean.._sd"           
##  [49] "fBodyBodyGyroJerkMag.std.._mean"          
##  [50] "fBodyBodyGyroJerkMag.std.._sd"            
##  [51] "fBodyBodyGyroMag.mean.._mean"             
##  [52] "fBodyBodyGyroMag.mean.._sd"               
##  [53] "fBodyBodyGyroMag.std.._mean"              
##  [54] "fBodyBodyGyroMag.std.._sd"                
##  [55] "fBodyGyro.mean...X_mean"                  
##  [56] "fBodyGyro.mean...X_sd"                    
##  [57] "fBodyGyro.mean...Y_mean"                  
##  [58] "fBodyGyro.mean...Y_sd"                    
##  [59] "fBodyGyro.mean...Z_mean"                  
##  [60] "fBodyGyro.mean...Z_sd"                    
##  [61] "fBodyGyro.std...X_mean"                   
##  [62] "fBodyGyro.std...X_sd"                     
##  [63] "fBodyGyro.std...Y_mean"                   
##  [64] "fBodyGyro.std...Y_sd"                     
##  [65] "fBodyGyro.std...Z_mean"                   
##  [66] "fBodyGyro.std...Z_sd"                     
##  [67] "tBodyAcc.mean...X_mean"                   
##  [68] "tBodyAcc.mean...X_sd"                     
##  [69] "tBodyAcc.mean...Y_mean"                   
##  [70] "tBodyAcc.mean...Y_sd"                     
##  [71] "tBodyAcc.mean...Z_mean"                   
##  [72] "tBodyAcc.mean...Z_sd"                     
##  [73] "tBodyAcc.std...X_mean"                    
##  [74] "tBodyAcc.std...X_sd"                      
##  [75] "tBodyAcc.std...Y_mean"                    
##  [76] "tBodyAcc.std...Y_sd"                      
##  [77] "tBodyAcc.std...Z_mean"                    
##  [78] "tBodyAcc.std...Z_sd"                      
##  [79] "tBodyAccJerk.mean...X_mean"               
##  [80] "tBodyAccJerk.mean...X_sd"                 
##  [81] "tBodyAccJerk.mean...Y_mean"               
##  [82] "tBodyAccJerk.mean...Y_sd"                 
##  [83] "tBodyAccJerk.mean...Z_mean"               
##  [84] "tBodyAccJerk.mean...Z_sd"                 
##  [85] "tBodyAccJerk.std...X_mean"                
##  [86] "tBodyAccJerk.std...X_sd"                  
##  [87] "tBodyAccJerk.std...Y_mean"                
##  [88] "tBodyAccJerk.std...Y_sd"                  
##  [89] "tBodyAccJerk.std...Z_mean"                
##  [90] "tBodyAccJerk.std...Z_sd"                  
##  [91] "tBodyAccJerkMag.mean.._mean"              
##  [92] "tBodyAccJerkMag.mean.._sd"                
##  [93] "tBodyAccJerkMag.std.._mean"               
##  [94] "tBodyAccJerkMag.std.._sd"                 
##  [95] "tBodyAccMag.mean.._mean"                  
##  [96] "tBodyAccMag.mean.._sd"                    
##  [97] "tBodyAccMag.std.._mean"                   
##  [98] "tBodyAccMag.std.._sd"                     
##  [99] "tBodyGyro.mean...X_mean"                  
## [100] "tBodyGyro.mean...X_sd"                    
## [101] "tBodyGyro.mean...Y_mean"                  
## [102] "tBodyGyro.mean...Y_sd"                    
## [103] "tBodyGyro.mean...Z_mean"                  
## [104] "tBodyGyro.mean...Z_sd"                    
## [105] "tBodyGyro.std...X_mean"                   
## [106] "tBodyGyro.std...X_sd"                     
## [107] "tBodyGyro.std...Y_mean"                   
## [108] "tBodyGyro.std...Y_sd"                     
## [109] "tBodyGyro.std...Z_mean"                   
## [110] "tBodyGyro.std...Z_sd"                     
## [111] "tBodyGyroJerk.mean...X_mean"              
## [112] "tBodyGyroJerk.mean...X_sd"                
## [113] "tBodyGyroJerk.mean...Y_mean"              
## [114] "tBodyGyroJerk.mean...Y_sd"                
## [115] "tBodyGyroJerk.mean...Z_mean"              
## [116] "tBodyGyroJerk.mean...Z_sd"                
## [117] "tBodyGyroJerk.std...X_mean"               
## [118] "tBodyGyroJerk.std...X_sd"                 
## [119] "tBodyGyroJerk.std...Y_mean"               
## [120] "tBodyGyroJerk.std...Y_sd"                 
## [121] "tBodyGyroJerk.std...Z_mean"               
## [122] "tBodyGyroJerk.std...Z_sd"                 
## [123] "tBodyGyroJerkMag.mean.._mean"             
## [124] "tBodyGyroJerkMag.mean.._sd"               
## [125] "tBodyGyroJerkMag.std.._mean"              
## [126] "tBodyGyroJerkMag.std.._sd"                
## [127] "tBodyGyroMag.mean.._mean"                 
## [128] "tBodyGyroMag.mean.._sd"                   
## [129] "tBodyGyroMag.std.._mean"                  
## [130] "tBodyGyroMag.std.._sd"                    
## [131] "tGravityAcc.mean...X_mean"                
## [132] "tGravityAcc.mean...X_sd"                  
## [133] "tGravityAcc.mean...Y_mean"                
## [134] "tGravityAcc.mean...Y_sd"                  
## [135] "tGravityAcc.mean...Z_mean"                
## [136] "tGravityAcc.mean...Z_sd"                  
## [137] "tGravityAcc.std...X_mean"                 
## [138] "tGravityAcc.std...X_sd"                   
## [139] "tGravityAcc.std...Y_mean"                 
## [140] "tGravityAcc.std...Y_sd"                   
## [141] "tGravityAcc.std...Z_mean"                 
## [142] "tGravityAcc.std...Z_sd"                   
## [143] "tGravityAccMag.mean.._mean"               
## [144] "tGravityAccMag.mean.._sd"                 
## [145] "tGravityAccMag.std.._mean"                
## [146] "tGravityAccMag.std.._sd"
```

##Value
Meaning: value of the summary statistic calculated.

Value: These floating point values. Units were not specified in the original data. 
  
