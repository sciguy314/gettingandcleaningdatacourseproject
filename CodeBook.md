#  Getting and Cleaning Data Course Project
##  CodeBook.md

## Data

The following description of the orginal data is taken from the README.txt file that accompanied the original data:

 
> Human Activity Recognition Using Smartphones Dataset  
> Version 1.0  
>  
> Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
> Smartlab - Non Linear Complex Systems Laboratory
> DITEN - Universit‡ degli Studi di Genova.
> Via Opera Pia 11A, I-16145, Genoa, Italy.
> activityrecognition@smartlab.ws
> www.smartlab.ws  
> 
> The experiments have been carried out with a group of 30 volunteers within an age bracket > of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 
> 
> The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 
> 
> For each record it is provided:  
>
> - Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
> - Triaxial Angular velocity from the gyroscope. 
> - A 561-feature vector with time and frequency domain variables. 
> - Its activity label. 
> - An identifier of the subject who carried out the experiment.
> 
> The dataset includes the following files:  
>
> - 'README.txt'
> 
> - 'features_info.txt': Shows information about the variables used on the feature vector.
> 
> - 'features.txt': List of all features.
> 
> - 'activity_labels.txt': Links the class labels with their activity name.
> 
> - 'train/X_train.txt': Training set.
> 
> - 'train/y_train.txt': Training labels.
> 
> - 'test/X_test.txt': Test set.
> 
> - 'test/y_test.txt': Test labels.
> 
> The following files are available for the train and test data. Their descriptions are equivalent. 
> 
> - 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 


## Variables

### Original Data Code Book

The following comes from the features.txt document distributed with the original data and describes how the data was collected and labeled in the data set.

>Feature Selection 
>
>The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 
>
>Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 
>
>Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 
>
>These signals were used to estimate variables of the feature vector for each pattern:  
>'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.
>
>tBodyAcc-XYZ  
>tGravityAcc-XYZ  
>tBodyAccJerk-XYZ  
>tBodyGyro-XYZ  
>tBodyGyroJerk-XYZ  
>tBodyAccMag  
>tGravityAccMag  
>tBodyAccJerkMag  
>tBodyGyroMag  
>tBodyGyroJerkMag  
>fBodyAcc-XYZ  
>fBodyAccJerk-XYZ  
>fBodyGyro-XYZ  
>fBodyAccMag  
>fBodyAccJerkMag  
>fBodyGyroMag  
>fBodyGyroJerkMag  
>
>The set of variables that were estimated from these signals are: 
>
>mean(): Mean value  
>std(): Standard deviation  
>mad(): Median absolute deviation   
>max(): Largest value in array  
>min(): Smallest value in array  
>sma(): Signal magnitude area  
>energy(): Energy measure. Sum of the squares divided by the number of values.
>iqr(): Interquartile range   
>entropy(): Signal entropy  
>arCoeff(): Autorregresion coefficients with Burg order equal to 4  
>correlation(): correlation coefficient between two signals  
>maxInds(): index of the frequency component with largest magnitude  
>meanFreq(): Weighted average of the frequency components to obtain a mean frequency  
>skewness(): skewness of the frequency domain signal   
>kurtosis(): kurtosis of the frequency domain signal   
>bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.  
>angle(): Angle between to vectors.  
>
>Additional vectors obtained by averaging the signals in a signal window sample. These are used on the angle() variable:
>
>gravityMean  
>tBodyAccMean  
>tBodyAccJerkMean  
>tBodyGyroMean  
>tBodyGyroJerkMean  
>
>The complete list of variables of each feature vector is available in 'features.txt'


### Original Data CodeBook

**NOTE: Since the data was normalized it has no units!**

These columns names were obtained from the **features.txt** file and are associated with the original data. The column names were edited within run_analysis.R to standardize their appearance. The following changes were made

* "()" were removed
* "-" were replaced with "."

This resulted in the following columns  

  Column Name -- Description of Contents  
subject -- Study participant identifier, 1...30  
activity -- Type of activity, factor, 6 levels, see   
type -- "Train" or "Test"  
tBodyAcc.mean.X      
   --  Time domain body accelerometer mean value in the X axis   
tBodyAcc.mean.Y      
   --  Time domain body accelerometer mean value in the Y axis   
tBodyAcc.mean.Z      
   --  Time domain body accelerometer mean value in the Z axis   
tBodyAcc.std.X       
   --  Time domain body accelerometer standard deviation in the X axis   
tBodyAcc.std.Y       
   --  Time domain body accelerometer standard deviation in the Y axis   
tBodyAcc.std.Z       
   --  Time domain body accelerometer standard deviation in the Z axis   
tBodyAcc.mad.X       
   --  Time domain body accelerometer median absolute deviationin the X axis   
tBodyAcc.mad.Y       
   --  Time domain body accelerometer median absolute deviationin the Y axis   
tBodyAcc.mad.Z       
   --  Time domain body accelerometer median absolute deviationin the Z axis   
tBodyAcc.max.X       
   --  Time domain body accelerometer maximum value in the X axis   
tBodyAcc.max.Y       
   --  Time domain body accelerometer maximum value in the Y axis   
tBodyAcc.max.Z       
   --  Time domain body accelerometer maximum value in the Z axis   
tBodyAcc.min.X       
   --  Time domain body accelerometer minimum value in the X axis   
tBodyAcc.min.Y       
   --  Time domain body accelerometer minimum value in the Y axis   
tBodyAcc.min.Z       
   --  Time domain body accelerometer minimum value in the Z axis   
tBodyAcc.sma         
   --  Time domain body accelerometer signal magnitude area   
tBodyAcc.energy.X        
   --  Time domain body accelerometer energy measure in the X axis   
tBodyAcc.energy.Y        
   --  Time domain body accelerometer energy measure in the Y axis   
tBodyAcc.energy.Z        
   --  Time domain body accelerometer energy measure in the Z axis   
tBodyAcc.iqr.X       
   --  Time domain body accelerometer interquartile range in the X axis   
tBodyAcc.iqr.Y       
   --  Time domain body accelerometer interquartile range in the Y axis   
tBodyAcc.iqr.Z       
   --  Time domain body accelerometer interquartile range in the Z axis   
tBodyAcc.entropy.X       
   --  Time domain body accelerometer signal entropy in the X axis   
tBodyAcc.entropy.Y       
   --  Time domain body accelerometer signal entropy in the Y axis   
tBodyAcc.entropy.Z       
   --  Time domain body accelerometer signal entropy in the Z axis   
tBodyAcc.arCoeff.X.1         
   --  Time domain body accelerometer autoregression coefficients in the X axis,1   
tBodyAcc.arCoeff.X.2         
   --  Time domain body accelerometer autoregression coefficients in the X axis,2   
tBodyAcc.arCoeff.X.3         
   --  Time domain body accelerometer autoregression coefficients in the X axis,3   
tBodyAcc.arCoeff.X.4         
   --  Time domain body accelerometer autoregression coefficients in the X axis,4   
tBodyAcc.arCoeff.Y.1         
   --  Time domain body accelerometer autoregression coefficients in the Y axis,1   
tBodyAcc.arCoeff.Y.2         
   --  Time domain body accelerometer autoregression coefficients in the Y axis,2   
tBodyAcc.arCoeff.Y.3         
   --  Time domain body accelerometer autoregression coefficients in the Y axis,3   
tBodyAcc.arCoeff.Y.4         
   --  Time domain body accelerometer autoregression coefficients in the Y axis,4   
tBodyAcc.arCoeff.Z.1         
   --  Time domain body accelerometer autoregression coefficients in the Z axis,1   
tBodyAcc.arCoeff.Z.2         
   --  Time domain body accelerometer autoregression coefficients in the Z axis,2   
tBodyAcc.arCoeff.Z.3         
   --  Time domain body accelerometer autoregression coefficients in the Z axis,3   
tBodyAcc.arCoeff.Z.4         
   --  Time domain body accelerometer autoregression coefficients in the Z axis,4   
tBodyAcc.correlation.X.Y         
   --  Time domain body accelerometer -correlation()in the X axis,Y   
tBodyAcc.correlation.X.Z         
   --  Time domain body accelerometer -correlation()in the X axis,Z   
tBodyAcc.correlation.Y.Z         
   --  Time domain body accelerometer -correlation()in the Y axis,Z   
tGravityAcc.mean.X       
   --  Time domain gravity accelerometer mean value in the X axis   
tGravityAcc.mean.Y       
   --  Time domain gravity accelerometer mean value in the Y axis   
tGravityAcc.mean.Z       
   --  Time domain gravity accelerometer mean value in the Z axis   
tGravityAcc.std.X        
   --  Time domain gravity accelerometer standard deviation in the X axis   
tGravityAcc.std.Y        
   --  Time domain gravity accelerometer standard deviation in the Y axis   
tGravityAcc.std.Z        
   --  Time domain gravity accelerometer standard deviation in the Z axis   
tGravityAcc.mad.X        
   --  Time domain gravity accelerometer median absolute deviationin the X axis   
tGravityAcc.mad.Y        
   --  Time domain gravity accelerometer median absolute deviationin the Y axis   
tGravityAcc.mad.Z        
   --  Time domain gravity accelerometer median absolute deviationin the Z axis   
tGravityAcc.max.X        
   --  Time domain gravity accelerometer maximum value in the X axis   
tGravityAcc.max.Y        
   --  Time domain gravity accelerometer maximum value in the Y axis   
tGravityAcc.max.Z        
   --  Time domain gravity accelerometer maximum value in the Z axis   
tGravityAcc.min.X        
   --  Time domain gravity accelerometer minimum value in the X axis   
tGravityAcc.min.Y        
   --  Time domain gravity accelerometer minimum value in the Y axis   
tGravityAcc.min.Z        
   --  Time domain gravity accelerometer minimum value in the Z axis   
tGravityAcc.sma      
   --  Time domain gravity accelerometer signal magnitude area   
tGravityAcc.energy.X         
   --  Time domain gravity accelerometer energy measure in the X axis   
tGravityAcc.energy.Y         
   --  Time domain gravity accelerometer energy measure in the Y axis   
tGravityAcc.energy.Z         
   --  Time domain gravity accelerometer energy measure in the Z axis   
tGravityAcc.iqr.X        
   --  Time domain gravity accelerometer interquartile range in the X axis   
tGravityAcc.iqr.Y        
   --  Time domain gravity accelerometer interquartile range in the Y axis   
tGravityAcc.iqr.Z        
   --  Time domain gravity accelerometer interquartile range in the Z axis   
tGravityAcc.entropy.X        
   --  Time domain gravity accelerometer signal entropy in the X axis   
tGravityAcc.entropy.Y        
   --  Time domain gravity accelerometer signal entropy in the Y axis   
tGravityAcc.entropy.Z        
   --  Time domain gravity accelerometer signal entropy in the Z axis   
tGravityAcc.arCoeff.X.1      
   --  Time domain gravity accelerometer autoregression coefficients in the X axis,1   
tGravityAcc.arCoeff.X.2      
   --  Time domain gravity accelerometer autoregression coefficients in the X axis,2   
tGravityAcc.arCoeff.X.3      
   --  Time domain gravity accelerometer autoregression coefficients in the X axis,3   
tGravityAcc.arCoeff.X.4      
   --  Time domain gravity accelerometer autoregression coefficients in the X axis,4   
tGravityAcc.arCoeff.Y.1      
   --  Time domain gravity accelerometer autoregression coefficients in the Y axis,1   
tGravityAcc.arCoeff.Y.2      
   --  Time domain gravity accelerometer autoregression coefficients in the Y axis,2   
tGravityAcc.arCoeff.Y.3      
   --  Time domain gravity accelerometer autoregression coefficients in the Y axis,3   
tGravityAcc.arCoeff.Y.4      
   --  Time domain gravity accelerometer autoregression coefficients in the Y axis,4   
tGravityAcc.arCoeff.Z.1      
   --  Time domain gravity accelerometer autoregression coefficients in the Z axis,1   
tGravityAcc.arCoeff.Z.2      
   --  Time domain gravity accelerometer autoregression coefficients in the Z axis,2   
tGravityAcc.arCoeff.Z.3      
   --  Time domain gravity accelerometer autoregression coefficients in the Z axis,3   
tGravityAcc.arCoeff.Z.4      
   --  Time domain gravity accelerometer autoregression coefficients in the Z axis,4   
tGravityAcc.correlation.X.Y          
   --  Time domain gravity accelerometer -correlation()in the X axis,Y   
tGravityAcc.correlation.X.Z          
   --  Time domain gravity accelerometer -correlation()in the X axis,Z   
tGravityAcc.correlation.Y.Z          
   --  Time domain gravity accelerometer -correlation()in the Y axis,Z   
tBodyAccJerk.mean.X          
   --  Time domain body accelerometer Jerkmean value in the X axis   
tBodyAccJerk.mean.Y          
   --  Time domain body accelerometer Jerkmean value in the Y axis   
tBodyAccJerk.mean.Z          
   --  Time domain body accelerometer Jerkmean value in the Z axis   
tBodyAccJerk.std.X       
   --  Time domain body accelerometer Jerkstandard deviation in the X axis   
tBodyAccJerk.std.Y       
   --  Time domain body accelerometer Jerkstandard deviation in the Y axis   
tBodyAccJerk.std.Z       
   --  Time domain body accelerometer Jerkstandard deviation in the Z axis   
tBodyAccJerk.mad.X       
   --  Time domain body accelerometer Jerkmedian absolute deviationin the X axis   
tBodyAccJerk.mad.Y       
   --  Time domain body accelerometer Jerkmedian absolute deviationin the Y axis   
tBodyAccJerk.mad.Z       
   --  Time domain body accelerometer Jerkmedian absolute deviationin the Z axis   
tBodyAccJerk.max.X       
   --  Time domain body accelerometer Jerkmaximum value in the X axis   
tBodyAccJerk.max.Y       
   --  Time domain body accelerometer Jerkmaximum value in the Y axis   
tBodyAccJerk.max.Z       
   --  Time domain body accelerometer Jerkmaximum value in the Z axis   
tBodyAccJerk.min.X       
   --  Time domain body accelerometer Jerkminimum value in the X axis   
tBodyAccJerk.min.Y       
   --  Time domain body accelerometer Jerkminimum value in the Y axis   
tBodyAccJerk.min.Z       
   --  Time domain body accelerometer Jerkminimum value in the Z axis   
tBodyAccJerk.sma         
   --  Time domain body accelerometer Jerksignal magnitude area   
tBodyAccJerk.energy.X        
   --  Time domain body accelerometer Jerkenergy measure in the X axis   
tBodyAccJerk.energy.Y        
   --  Time domain body accelerometer Jerkenergy measure in the Y axis   
tBodyAccJerk.energy.Z        
   --  Time domain body accelerometer Jerkenergy measure in the Z axis   
tBodyAccJerk.iqr.X       
   --  Time domain body accelerometer Jerkinterquartile range in the X axis   
tBodyAccJerk.iqr.Y       
   --  Time domain body accelerometer Jerkinterquartile range in the Y axis   
tBodyAccJerk.iqr.Z       
   --  Time domain body accelerometer Jerkinterquartile range in the Z axis   
tBodyAccJerk.entropy.X       
   --  Time domain body accelerometer Jerksignal entropy in the X axis   
tBodyAccJerk.entropy.Y       
   --  Time domain body accelerometer Jerksignal entropy in the Y axis   
tBodyAccJerk.entropy.Z       
   --  Time domain body accelerometer Jerksignal entropy in the Z axis   
tBodyAccJerk.arCoeff.X.1         
   --  Time domain body accelerometer Jerkautoregression coefficients in the X axis,1   
tBodyAccJerk.arCoeff.X.2         
   --  Time domain body accelerometer Jerkautoregression coefficients in the X axis,2   
tBodyAccJerk.arCoeff.X.3         
   --  Time domain body accelerometer Jerkautoregression coefficients in the X axis,3   
tBodyAccJerk.arCoeff.X.4         
   --  Time domain body accelerometer Jerkautoregression coefficients in the X axis,4   
tBodyAccJerk.arCoeff.Y.1         
   --  Time domain body accelerometer Jerkautoregression coefficients in the Y axis,1   
tBodyAccJerk.arCoeff.Y.2         
   --  Time domain body accelerometer Jerkautoregression coefficients in the Y axis,2   
tBodyAccJerk.arCoeff.Y.3         
   --  Time domain body accelerometer Jerkautoregression coefficients in the Y axis,3   
tBodyAccJerk.arCoeff.Y.4         
   --  Time domain body accelerometer Jerkautoregression coefficients in the Y axis,4   
tBodyAccJerk.arCoeff.Z.1         
   --  Time domain body accelerometer Jerkautoregression coefficients in the Z axis,1   
tBodyAccJerk.arCoeff.Z.2         
   --  Time domain body accelerometer Jerkautoregression coefficients in the Z axis,2   
tBodyAccJerk.arCoeff.Z.3         
   --  Time domain body accelerometer Jerkautoregression coefficients in the Z axis,3   
tBodyAccJerk.arCoeff.Z.4         
   --  Time domain body accelerometer Jerkautoregression coefficients in the Z axis,4   
tBodyAccJerk.correlation.X.Y         
   --  Time domain body accelerometer Jerk-correlation()in the X axis,Y   
tBodyAccJerk.correlation.X.Z         
   --  Time domain body accelerometer Jerk-correlation()in the X axis,Z   
tBodyAccJerk.correlation.Y.Z         
   --  Time domain body accelerometer Jerk-correlation()in the Y axis,Z   
tBodyGyro.mean.X         
   --  Time domain body gyroscope mean value in the X axis   
tBodyGyro.mean.Y         
   --  Time domain body gyroscope mean value in the Y axis   
tBodyGyro.mean.Z         
   --  Time domain body gyroscope mean value in the Z axis   
tBodyGyro.std.X      
   --  Time domain body gyroscope standard deviation in the X axis   
tBodyGyro.std.Y      
   --  Time domain body gyroscope standard deviation in the Y axis   
tBodyGyro.std.Z      
   --  Time domain body gyroscope standard deviation in the Z axis   
tBodyGyro.mad.X      
   --  Time domain body gyroscope median absolute deviationin the X axis   
tBodyGyro.mad.Y      
   --  Time domain body gyroscope median absolute deviationin the Y axis   
tBodyGyro.mad.Z      
   --  Time domain body gyroscope median absolute deviationin the Z axis   
tBodyGyro.max.X      
   --  Time domain body gyroscope maximum value in the X axis   
tBodyGyro.max.Y      
   --  Time domain body gyroscope maximum value in the Y axis   
tBodyGyro.max.Z      
   --  Time domain body gyroscope maximum value in the Z axis   
tBodyGyro.min.X      
   --  Time domain body gyroscope minimum value in the X axis   
tBodyGyro.min.Y      
   --  Time domain body gyroscope minimum value in the Y axis   
tBodyGyro.min.Z      
   --  Time domain body gyroscope minimum value in the Z axis   
tBodyGyro.sma        
   --  Time domain body gyroscope signal magnitude area   
tBodyGyro.energy.X       
   --  Time domain body gyroscope energy measure in the X axis   
tBodyGyro.energy.Y       
   --  Time domain body gyroscope energy measure in the Y axis   
tBodyGyro.energy.Z       
   --  Time domain body gyroscope energy measure in the Z axis   
tBodyGyro.iqr.X      
   --  Time domain body gyroscope interquartile range in the X axis   
tBodyGyro.iqr.Y      
   --  Time domain body gyroscope interquartile range in the Y axis   
tBodyGyro.iqr.Z      
   --  Time domain body gyroscope interquartile range in the Z axis   
tBodyGyro.entropy.X      
   --  Time domain body gyroscope signal entropy in the X axis   
tBodyGyro.entropy.Y      
   --  Time domain body gyroscope signal entropy in the Y axis   
tBodyGyro.entropy.Z      
   --  Time domain body gyroscope signal entropy in the Z axis   
tBodyGyro.arCoeff.X.1        
   --  Time domain body gyroscope autoregression coefficients in the X axis,1   
tBodyGyro.arCoeff.X.2        
   --  Time domain body gyroscope autoregression coefficients in the X axis,2   
tBodyGyro.arCoeff.X.3        
   --  Time domain body gyroscope autoregression coefficients in the X axis,3   
tBodyGyro.arCoeff.X.4        
   --  Time domain body gyroscope autoregression coefficients in the X axis,4   
tBodyGyro.arCoeff.Y.1        
   --  Time domain body gyroscope autoregression coefficients in the Y axis,1   
tBodyGyro.arCoeff.Y.2        
   --  Time domain body gyroscope autoregression coefficients in the Y axis,2   
tBodyGyro.arCoeff.Y.3        
   --  Time domain body gyroscope autoregression coefficients in the Y axis,3   
tBodyGyro.arCoeff.Y.4        
   --  Time domain body gyroscope autoregression coefficients in the Y axis,4   
tBodyGyro.arCoeff.Z.1        
   --  Time domain body gyroscope autoregression coefficients in the Z axis,1   
tBodyGyro.arCoeff.Z.2        
   --  Time domain body gyroscope autoregression coefficients in the Z axis,2   
tBodyGyro.arCoeff.Z.3        
   --  Time domain body gyroscope autoregression coefficients in the Z axis,3   
tBodyGyro.arCoeff.Z.4        
   --  Time domain body gyroscope autoregression coefficients in the Z axis,4   
tBodyGyro.correlation.X.Y        
   --  Time domain body gyroscope -correlation()in the X axis,Y   
tBodyGyro.correlation.X.Z        
   --  Time domain body gyroscope -correlation()in the X axis,Z   
tBodyGyro.correlation.Y.Z        
   --  Time domain body gyroscope -correlation()in the Y axis,Z   
tBodyGyroJerk.mean.X         
   --  Time domain body gyroscope Jerkmean value in the X axis   
tBodyGyroJerk.mean.Y         
   --  Time domain body gyroscope Jerkmean value in the Y axis   
tBodyGyroJerk.mean.Z         
   --  Time domain body gyroscope Jerkmean value in the Z axis   
tBodyGyroJerk.std.X      
   --  Time domain body gyroscope Jerkstandard deviation in the X axis   
tBodyGyroJerk.std.Y      
   --  Time domain body gyroscope Jerkstandard deviation in the Y axis   
tBodyGyroJerk.std.Z      
   --  Time domain body gyroscope Jerkstandard deviation in the Z axis   
tBodyGyroJerk.mad.X      
   --  Time domain body gyroscope Jerkmedian absolute deviationin the X axis   
tBodyGyroJerk.mad.Y      
   --  Time domain body gyroscope Jerkmedian absolute deviationin the Y axis   
tBodyGyroJerk.mad.Z      
   --  Time domain body gyroscope Jerkmedian absolute deviationin the Z axis   
tBodyGyroJerk.max.X      
   --  Time domain body gyroscope Jerkmaximum value in the X axis   
tBodyGyroJerk.max.Y      
   --  Time domain body gyroscope Jerkmaximum value in the Y axis   
tBodyGyroJerk.max.Z      
   --  Time domain body gyroscope Jerkmaximum value in the Z axis   
tBodyGyroJerk.min.X      
   --  Time domain body gyroscope Jerkminimum value in the X axis   
tBodyGyroJerk.min.Y      
   --  Time domain body gyroscope Jerkminimum value in the Y axis   
tBodyGyroJerk.min.Z      
   --  Time domain body gyroscope Jerkminimum value in the Z axis   
tBodyGyroJerk.sma        
   --  Time domain body gyroscope Jerksignal magnitude area   
tBodyGyroJerk.energy.X       
   --  Time domain body gyroscope Jerkenergy measure in the X axis   
tBodyGyroJerk.energy.Y       
   --  Time domain body gyroscope Jerkenergy measure in the Y axis   
tBodyGyroJerk.energy.Z       
   --  Time domain body gyroscope Jerkenergy measure in the Z axis   
tBodyGyroJerk.iqr.X      
   --  Time domain body gyroscope Jerkinterquartile range in the X axis   
tBodyGyroJerk.iqr.Y      
   --  Time domain body gyroscope Jerkinterquartile range in the Y axis   
tBodyGyroJerk.iqr.Z      
   --  Time domain body gyroscope Jerkinterquartile range in the Z axis   
tBodyGyroJerk.entropy.X      
   --  Time domain body gyroscope Jerksignal entropy in the X axis   
tBodyGyroJerk.entropy.Y      
   --  Time domain body gyroscope Jerksignal entropy in the Y axis   
tBodyGyroJerk.entropy.Z      
   --  Time domain body gyroscope Jerksignal entropy in the Z axis   
tBodyGyroJerk.arCoeff.X.1        
   --  Time domain body gyroscope Jerkautoregression coefficients in the X axis,1   
tBodyGyroJerk.arCoeff.X.2        
   --  Time domain body gyroscope Jerkautoregression coefficients in the X axis,2   
tBodyGyroJerk.arCoeff.X.3        
   --  Time domain body gyroscope Jerkautoregression coefficients in the X axis,3   
tBodyGyroJerk.arCoeff.X.4        
   --  Time domain body gyroscope Jerkautoregression coefficients in the X axis,4   
tBodyGyroJerk.arCoeff.Y.1        
   --  Time domain body gyroscope Jerkautoregression coefficients in the Y axis,1   
tBodyGyroJerk.arCoeff.Y.2        
   --  Time domain body gyroscope Jerkautoregression coefficients in the Y axis,2   
tBodyGyroJerk.arCoeff.Y.3        
   --  Time domain body gyroscope Jerkautoregression coefficients in the Y axis,3   
tBodyGyroJerk.arCoeff.Y.4        
   --  Time domain body gyroscope Jerkautoregression coefficients in the Y axis,4   
tBodyGyroJerk.arCoeff.Z.1        
   --  Time domain body gyroscope Jerkautoregression coefficients in the Z axis,1   
tBodyGyroJerk.arCoeff.Z.2        
   --  Time domain body gyroscope Jerkautoregression coefficients in the Z axis,2   
tBodyGyroJerk.arCoeff.Z.3        
   --  Time domain body gyroscope Jerkautoregression coefficients in the Z axis,3   
tBodyGyroJerk.arCoeff.Z.4        
   --  Time domain body gyroscope Jerkautoregression coefficients in the Z axis,4   
tBodyGyroJerk.correlation.X.Y        
   --  Time domain body gyroscope Jerk-correlation()in the X axis,Y   
tBodyGyroJerk.correlation.X.Z        
   --  Time domain body gyroscope Jerk-correlation()in the X axis,Z   
tBodyGyroJerk.correlation.Y.Z        
   --  Time domain body gyroscope Jerk-correlation()in the Y axis,Z   
tBodyAccMag.mean         
   --  Time domain body accelerometer Magmean value    
tBodyAccMag.std      
   --  Time domain body accelerometer Magstandard deviation    
tBodyAccMag.mad      
   --  Time domain body accelerometer Magmedian absolute deviation   
tBodyAccMag.max      
   --  Time domain body accelerometer Magmaximum value    
tBodyAccMag.min      
   --  Time domain body accelerometer Magminimum value    
tBodyAccMag.sma      
   --  Time domain body accelerometer Magsignal magnitude area   
tBodyAccMag.energy       
   --  Time domain body accelerometer Magenergy measure    
tBodyAccMag.iqr      
   --  Time domain body accelerometer Maginterquartile range    
tBodyAccMag.entropy      
   --  Time domain body accelerometer Magsignal entropy    
tBodyAccMag.arCoeff1         
   --  Time domain body accelerometer Magautoregression coefficients 1   
tBodyAccMag.arCoeff2         
   --  Time domain body accelerometer Magautoregression coefficients 2   
tBodyAccMag.arCoeff3         
   --  Time domain body accelerometer Magautoregression coefficients 3   
tBodyAccMag.arCoeff4         
   --  Time domain body accelerometer Magautoregression coefficients 4   
tGravityAccMag.mean          
   --  Time domain gravity accelerometer Magmean value    
tGravityAccMag.std       
   --  Time domain gravity accelerometer Magstandard deviation    
tGravityAccMag.mad       
   --  Time domain gravity accelerometer Magmedian absolute deviation   
tGravityAccMag.max       
   --  Time domain gravity accelerometer Magmaximum value    
tGravityAccMag.min       
   --  Time domain gravity accelerometer Magminimum value    
tGravityAccMag.sma       
   --  Time domain gravity accelerometer Magsignal magnitude area   
tGravityAccMag.energy        
   --  Time domain gravity accelerometer Magenergy measure    
tGravityAccMag.iqr       
   --  Time domain gravity accelerometer Maginterquartile range    
tGravityAccMag.entropy       
   --  Time domain gravity accelerometer Magsignal entropy    
tGravityAccMag.arCoeff1          
   --  Time domain gravity accelerometer Magautoregression coefficients 1   
tGravityAccMag.arCoeff2          
   --  Time domain gravity accelerometer Magautoregression coefficients 2   
tGravityAccMag.arCoeff3          
   --  Time domain gravity accelerometer Magautoregression coefficients 3   
tGravityAccMag.arCoeff4          
   --  Time domain gravity accelerometer Magautoregression coefficients 4   
tBodyAccJerkMag.mean         
   --  Time domain body accelerometer JerkMagmean value    
tBodyAccJerkMag.std          
   --  Time domain body accelerometer JerkMagstandard deviation    
tBodyAccJerkMag.mad          
   --  Time domain body accelerometer JerkMagmedian absolute deviation   
tBodyAccJerkMag.max          
   --  Time domain body accelerometer JerkMagmaximum value    
tBodyAccJerkMag.min          
   --  Time domain body accelerometer JerkMagminimum value    
tBodyAccJerkMag.sma          
   --  Time domain body accelerometer JerkMagsignal magnitude area   
tBodyAccJerkMag.energy       
   --  Time domain body accelerometer JerkMagenergy measure    
tBodyAccJerkMag.iqr          
   --  Time domain body accelerometer JerkMaginterquartile range    
tBodyAccJerkMag.entropy          
   --  Time domain body accelerometer JerkMagsignal entropy    
tBodyAccJerkMag.arCoeff1         
   --  Time domain body accelerometer JerkMagautoregression coefficients 1   
tBodyAccJerkMag.arCoeff2         
   --  Time domain body accelerometer JerkMagautoregression coefficients 2   
tBodyAccJerkMag.arCoeff3         
   --  Time domain body accelerometer JerkMagautoregression coefficients 3   
tBodyAccJerkMag.arCoeff4         
   --  Time domain body accelerometer JerkMagautoregression coefficients 4   
tBodyGyroMag.mean        
   --  Time domain body gyroscope Magmean value    
tBodyGyroMag.std         
   --  Time domain body gyroscope Magstandard deviation    
tBodyGyroMag.mad         
   --  Time domain body gyroscope Magmedian absolute deviation   
tBodyGyroMag.max         
   --  Time domain body gyroscope Magmaximum value    
tBodyGyroMag.min         
   --  Time domain body gyroscope Magminimum value    
tBodyGyroMag.sma         
   --  Time domain body gyroscope Magsignal magnitude area   
tBodyGyroMag.energy          
   --  Time domain body gyroscope Magenergy measure    
tBodyGyroMag.iqr         
   --  Time domain body gyroscope Maginterquartile range    
tBodyGyroMag.entropy         
   --  Time domain body gyroscope Magsignal entropy    
tBodyGyroMag.arCoeff1        
   --  Time domain body gyroscope Magautoregression coefficients 1   
tBodyGyroMag.arCoeff2        
   --  Time domain body gyroscope Magautoregression coefficients 2   
tBodyGyroMag.arCoeff3        
   --  Time domain body gyroscope Magautoregression coefficients 3   
tBodyGyroMag.arCoeff4        
   --  Time domain body gyroscope Magautoregression coefficients 4   
tBodyGyroJerkMag.mean        
   --  Time domain body gyroscope JerkMagmean value    
tBodyGyroJerkMag.std         
   --  Time domain body gyroscope JerkMagstandard deviation    
tBodyGyroJerkMag.mad         
   --  Time domain body gyroscope JerkMagmedian absolute deviation   
tBodyGyroJerkMag.max         
   --  Time domain body gyroscope JerkMagmaximum value    
tBodyGyroJerkMag.min         
   --  Time domain body gyroscope JerkMagminimum value    
tBodyGyroJerkMag.sma         
   --  Time domain body gyroscope JerkMagsignal magnitude area   
tBodyGyroJerkMag.energy          
   --  Time domain body gyroscope JerkMagenergy measure    
tBodyGyroJerkMag.iqr         
   --  Time domain body gyroscope JerkMaginterquartile range    
tBodyGyroJerkMag.entropy         
   --  Time domain body gyroscope JerkMagsignal entropy    
tBodyGyroJerkMag.arCoeff1        
   --  Time domain body gyroscope JerkMagautoregression coefficients 1   
tBodyGyroJerkMag.arCoeff2        
   --  Time domain body gyroscope JerkMagautoregression coefficients 2   
tBodyGyroJerkMag.arCoeff3        
   --  Time domain body gyroscope JerkMagautoregression coefficients 3   
tBodyGyroJerkMag.arCoeff4        
   --  Time domain body gyroscope JerkMagautoregression coefficients 4   
fBodyAcc.mean.X      
   --  FFT body accelerometer mean value in the X axis   
fBodyAcc.mean.Y      
   --  FFT body accelerometer mean value in the Y axis   
fBodyAcc.mean.Z      
   --  FFT body accelerometer mean value in the Z axis   
fBodyAcc.std.X       
   --  FFT body accelerometer standard deviation in the X axis   
fBodyAcc.std.Y       
   --  FFT body accelerometer standard deviation in the Y axis   
fBodyAcc.std.Z       
   --  FFT body accelerometer standard deviation in the Z axis   
fBodyAcc.mad.X       
   --  FFT body accelerometer median absolute deviationin the X axis   
fBodyAcc.mad.Y       
   --  FFT body accelerometer median absolute deviationin the Y axis   
fBodyAcc.mad.Z       
   --  FFT body accelerometer median absolute deviationin the Z axis   
fBodyAcc.max.X       
   --  FFT body accelerometer maximum value in the X axis   
fBodyAcc.max.Y       
   --  FFT body accelerometer maximum value in the Y axis   
fBodyAcc.max.Z       
   --  FFT body accelerometer maximum value in the Z axis   
fBodyAcc.min.X       
   --  FFT body accelerometer minimum value in the X axis   
fBodyAcc.min.Y       
   --  FFT body accelerometer minimum value in the Y axis   
fBodyAcc.min.Z       
   --  FFT body accelerometer minimum value in the Z axis   
fBodyAcc.sma         
   --  FFT body accelerometer signal magnitude area   
fBodyAcc.energy.X        
   --  FFT body accelerometer energy measure in the X axis   
fBodyAcc.energy.Y        
   --  FFT body accelerometer energy measure in the Y axis   
fBodyAcc.energy.Z        
   --  FFT body accelerometer energy measure in the Z axis   
fBodyAcc.iqr.X       
   --  FFT body accelerometer interquartile range in the X axis   
fBodyAcc.iqr.Y       
   --  FFT body accelerometer interquartile range in the Y axis   
fBodyAcc.iqr.Z       
   --  FFT body accelerometer interquartile range in the Z axis   
fBodyAcc.entropy.X       
   --  FFT body accelerometer signal entropy in the X axis   
fBodyAcc.entropy.Y       
   --  FFT body accelerometer signal entropy in the Y axis   
fBodyAcc.entropy.Z       
   --  FFT body accelerometer signal entropy in the Z axis   
fBodyAcc.maxInds.X       
   --  FFT body accelerometer -maxIndsin the X axis   
fBodyAcc.maxInds.Y       
   --  FFT body accelerometer -maxIndsin the Y axis   
fBodyAcc.maxInds.Z       
   --  FFT body accelerometer -maxIndsin the Z axis   
fBodyAcc.meanFreq.X      
   --  FFT body accelerometer weighted average of the frequency components in the X axis   
fBodyAcc.meanFreq.Y      
   --  FFT body accelerometer weighted average of the frequency components in the Y axis   
fBodyAcc.meanFreq.Z      
   --  FFT body accelerometer weighted average of the frequency components in the Z axis   
fBodyAcc.skewness.X      
   --  FFT body accelerometer skewness of the frequency domain signal in the X axis   
fBodyAcc.kurtosis.X      
   --  FFT body accelerometer kurtosis of the frequency domain signal in the X axis   
fBodyAcc.skewness.Y      
   --  FFT body accelerometer skewness of the frequency domain signal in the Y axis   
fBodyAcc.kurtosis.Y      
   --  FFT body accelerometer kurtosis of the frequency domain signal in the Y axis   
fBodyAcc.skewness.Z      
   --  FFT body accelerometer skewness of the frequency domain signal in the Z axis   
fBodyAcc.kurtosis.Z      
   --  FFT body accelerometer kurtosis of the frequency domain signal in the Z axis   
fBodyAcc.bandsEnergy.1.8         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -1,8   
fBodyAcc.bandsEnergy.9.16        
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -9,16   
fBodyAcc.bandsEnergy.17.24       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -17,24   
fBodyAcc.bandsEnergy.25.32       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -25,32   
fBodyAcc.bandsEnergy.33.40       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -33,40   
fBodyAcc.bandsEnergy.41.48       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -41,48   
fBodyAcc.bandsEnergy.49.56       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -49,56   
fBodyAcc.bandsEnergy.57.64       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -57,64   
fBodyAcc.bandsEnergy.1.16        
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -1,16   
fBodyAcc.bandsEnergy.17.32       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -17,32   
fBodyAcc.bandsEnergy.33.48       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -33,48   
fBodyAcc.bandsEnergy.49.64       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -49,64   
fBodyAcc.bandsEnergy.1.24        
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -1,24   
fBodyAcc.bandsEnergy.25.48       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -25,48   
fBodyAcc.bandsEnergy.1.8.1       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -1,8   
fBodyAcc.bandsEnergy.9.16.1      
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -9,16   
fBodyAcc.bandsEnergy.17.24.1         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -17,24   
fBodyAcc.bandsEnergy.25.32.1         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -25,32   
fBodyAcc.bandsEnergy.33.40.1         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -33,40   
fBodyAcc.bandsEnergy.41.48.1         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -41,48   
fBodyAcc.bandsEnergy.49.56.1         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -49,56   
fBodyAcc.bandsEnergy.57.64.1         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -57,64   
fBodyAcc.bandsEnergy.1.16.1      
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -1,16   
fBodyAcc.bandsEnergy.17.32.1         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -17,32   
fBodyAcc.bandsEnergy.33.48.1         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -33,48   
fBodyAcc.bandsEnergy.49.64.1         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -49,64   
fBodyAcc.bandsEnergy.1.24.1      
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -1,24   
fBodyAcc.bandsEnergy.25.48.1         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -25,48   
fBodyAcc.bandsEnergy.1.8.2       
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -1,8   
fBodyAcc.bandsEnergy.9.16.2      
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -9,16   
fBodyAcc.bandsEnergy.17.24.2         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -17,24   
fBodyAcc.bandsEnergy.25.32.2         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -25,32   
fBodyAcc.bandsEnergy.33.40.2         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -33,40   
fBodyAcc.bandsEnergy.41.48.2         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -41,48   
fBodyAcc.bandsEnergy.49.56.2         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -49,56   
fBodyAcc.bandsEnergy.57.64.2         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -57,64   
fBodyAcc.bandsEnergy.1.16.2      
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -1,16   
fBodyAcc.bandsEnergy.17.32.2         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -17,32   
fBodyAcc.bandsEnergy.33.48.2         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -33,48   
fBodyAcc.bandsEnergy.49.64.2         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -49,64   
fBodyAcc.bandsEnergy.1.24.2      
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -1,24   
fBodyAcc.bandsEnergy.25.48.2         
   --  FFT body accelerometer energy of a frequency interval within 64 bins of the FFT -25,48   
fBodyAccJerk.mean.X      
   --  FFT body accelerometer Jerkmean value in the X axis   
fBodyAccJerk.mean.Y      
   --  FFT body accelerometer Jerkmean value in the Y axis   
fBodyAccJerk.mean.Z      
   --  FFT body accelerometer Jerkmean value in the Z axis   
fBodyAccJerk.std.X       
   --  FFT body accelerometer Jerkstandard deviation in the X axis   
fBodyAccJerk.std.Y       
   --  FFT body accelerometer Jerkstandard deviation in the Y axis   
fBodyAccJerk.std.Z       
   --  FFT body accelerometer Jerkstandard deviation in the Z axis   
fBodyAccJerk.mad.X       
   --  FFT body accelerometer Jerkmedian absolute deviationin the X axis   
fBodyAccJerk.mad.Y       
   --  FFT body accelerometer Jerkmedian absolute deviationin the Y axis   
fBodyAccJerk.mad.Z       
   --  FFT body accelerometer Jerkmedian absolute deviationin the Z axis   
fBodyAccJerk.max.X       
   --  FFT body accelerometer Jerkmaximum value in the X axis   
fBodyAccJerk.max.Y       
   --  FFT body accelerometer Jerkmaximum value in the Y axis   
fBodyAccJerk.max.Z       
   --  FFT body accelerometer Jerkmaximum value in the Z axis   
fBodyAccJerk.min.X       
   --  FFT body accelerometer Jerkminimum value in the X axis   
fBodyAccJerk.min.Y       
   --  FFT body accelerometer Jerkminimum value in the Y axis   
fBodyAccJerk.min.Z       
   --  FFT body accelerometer Jerkminimum value in the Z axis   
fBodyAccJerk.sma         
   --  FFT body accelerometer Jerksignal magnitude area   
fBodyAccJerk.energy.X        
   --  FFT body accelerometer Jerkenergy measure in the X axis   
fBodyAccJerk.energy.Y        
   --  FFT body accelerometer Jerkenergy measure in the Y axis   
fBodyAccJerk.energy.Z        
   --  FFT body accelerometer Jerkenergy measure in the Z axis   
fBodyAccJerk.iqr.X       
   --  FFT body accelerometer Jerkinterquartile range in the X axis   
fBodyAccJerk.iqr.Y       
   --  FFT body accelerometer Jerkinterquartile range in the Y axis   
fBodyAccJerk.iqr.Z       
   --  FFT body accelerometer Jerkinterquartile range in the Z axis   
fBodyAccJerk.entropy.X       
   --  FFT body accelerometer Jerksignal entropy in the X axis   
fBodyAccJerk.entropy.Y       
   --  FFT body accelerometer Jerksignal entropy in the Y axis   
fBodyAccJerk.entropy.Z       
   --  FFT body accelerometer Jerksignal entropy in the Z axis   
fBodyAccJerk.maxInds.X       
   --  FFT body accelerometer Jerk-maxIndsin the X axis   
fBodyAccJerk.maxInds.Y       
   --  FFT body accelerometer Jerk-maxIndsin the Y axis   
fBodyAccJerk.maxInds.Z       
   --  FFT body accelerometer Jerk-maxIndsin the Z axis   
fBodyAccJerk.meanFreq.X      
   --  FFT body accelerometer Jerkweighted average of the frequency components in the X axis   
fBodyAccJerk.meanFreq.Y      
   --  FFT body accelerometer Jerkweighted average of the frequency components in the Y axis   
fBodyAccJerk.meanFreq.Z      
   --  FFT body accelerometer Jerkweighted average of the frequency components in the Z axis   
fBodyAccJerk.skewness.X      
   --  FFT body accelerometer Jerkskewness of the frequency domain signal in the X axis   
fBodyAccJerk.kurtosis.X      
   --  FFT body accelerometer Jerkkurtosis of the frequency domain signal in the X axis   
fBodyAccJerk.skewness.Y      
   --  FFT body accelerometer Jerkskewness of the frequency domain signal in the Y axis   
fBodyAccJerk.kurtosis.Y      
   --  FFT body accelerometer Jerkkurtosis of the frequency domain signal in the Y axis   
fBodyAccJerk.skewness.Z      
   --  FFT body accelerometer Jerkskewness of the frequency domain signal in the Z axis   
fBodyAccJerk.kurtosis.Z      
   --  FFT body accelerometer Jerkkurtosis of the frequency domain signal in the Z axis   
fBodyAccJerk.bandsEnergy.1.8         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -1,8   
fBodyAccJerk.bandsEnergy.9.16        
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -9,16   
fBodyAccJerk.bandsEnergy.17.24       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -17,24   
fBodyAccJerk.bandsEnergy.25.32       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -25,32   
fBodyAccJerk.bandsEnergy.33.40       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -33,40   
fBodyAccJerk.bandsEnergy.41.48       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -41,48   
fBodyAccJerk.bandsEnergy.49.56       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -49,56   
fBodyAccJerk.bandsEnergy.57.64       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -57,64   
fBodyAccJerk.bandsEnergy.1.16        
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -1,16   
fBodyAccJerk.bandsEnergy.17.32       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -17,32   
fBodyAccJerk.bandsEnergy.33.48       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -33,48   
fBodyAccJerk.bandsEnergy.49.64       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -49,64   
fBodyAccJerk.bandsEnergy.1.24        
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -1,24   
fBodyAccJerk.bandsEnergy.25.48       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -25,48   
fBodyAccJerk.bandsEnergy.1.8.1       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -1,8   
fBodyAccJerk.bandsEnergy.9.16.1      
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -9,16   
fBodyAccJerk.bandsEnergy.17.24.1         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -17,24   
fBodyAccJerk.bandsEnergy.25.32.1         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -25,32   
fBodyAccJerk.bandsEnergy.33.40.1         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -33,40   
fBodyAccJerk.bandsEnergy.41.48.1         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -41,48   
fBodyAccJerk.bandsEnergy.49.56.1         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -49,56   
fBodyAccJerk.bandsEnergy.57.64.1         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -57,64   
fBodyAccJerk.bandsEnergy.1.16.1      
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -1,16   
fBodyAccJerk.bandsEnergy.17.32.1         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -17,32   
fBodyAccJerk.bandsEnergy.33.48.1         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -33,48   
fBodyAccJerk.bandsEnergy.49.64.1         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -49,64   
fBodyAccJerk.bandsEnergy.1.24.1      
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -1,24   
fBodyAccJerk.bandsEnergy.25.48.1         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -25,48   
fBodyAccJerk.bandsEnergy.1.8.2       
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -1,8   
fBodyAccJerk.bandsEnergy.9.16.2      
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -9,16   
fBodyAccJerk.bandsEnergy.17.24.2         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -17,24   
fBodyAccJerk.bandsEnergy.25.32.2         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -25,32   
fBodyAccJerk.bandsEnergy.33.40.2         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -33,40   
fBodyAccJerk.bandsEnergy.41.48.2         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -41,48   
fBodyAccJerk.bandsEnergy.49.56.2         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -49,56   
fBodyAccJerk.bandsEnergy.57.64.2         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -57,64   
fBodyAccJerk.bandsEnergy.1.16.2      
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -1,16   
fBodyAccJerk.bandsEnergy.17.32.2         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -17,32   
fBodyAccJerk.bandsEnergy.33.48.2         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -33,48   
fBodyAccJerk.bandsEnergy.49.64.2         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -49,64   
fBodyAccJerk.bandsEnergy.1.24.2      
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -1,24   
fBodyAccJerk.bandsEnergy.25.48.2         
   --  FFT body accelerometer Jerkenergy of a frequency interval within 64 bins of the FFT -25,48   
fBodyGyro.mean.X         
   --  FFT body gyroscope mean value in the X axis   
fBodyGyro.mean.Y         
   --  FFT body gyroscope mean value in the Y axis   
fBodyGyro.mean.Z         
   --  FFT body gyroscope mean value in the Z axis   
fBodyGyro.std.X      
   --  FFT body gyroscope standard deviation in the X axis   
fBodyGyro.std.Y      
   --  FFT body gyroscope standard deviation in the Y axis   
fBodyGyro.std.Z      
   --  FFT body gyroscope standard deviation in the Z axis   
fBodyGyro.mad.X      
   --  FFT body gyroscope median absolute deviationin the X axis   
fBodyGyro.mad.Y      
   --  FFT body gyroscope median absolute deviationin the Y axis   
fBodyGyro.mad.Z      
   --  FFT body gyroscope median absolute deviationin the Z axis   
fBodyGyro.max.X      
   --  FFT body gyroscope maximum value in the X axis   
fBodyGyro.max.Y      
   --  FFT body gyroscope maximum value in the Y axis   
fBodyGyro.max.Z      
   --  FFT body gyroscope maximum value in the Z axis   
fBodyGyro.min.X      
   --  FFT body gyroscope minimum value in the X axis   
fBodyGyro.min.Y      
   --  FFT body gyroscope minimum value in the Y axis   
fBodyGyro.min.Z      
   --  FFT body gyroscope minimum value in the Z axis   
fBodyGyro.sma        
   --  FFT body gyroscope signal magnitude area   
fBodyGyro.energy.X       
   --  FFT body gyroscope energy measure in the X axis   
fBodyGyro.energy.Y       
   --  FFT body gyroscope energy measure in the Y axis   
fBodyGyro.energy.Z       
   --  FFT body gyroscope energy measure in the Z axis   
fBodyGyro.iqr.X      
   --  FFT body gyroscope interquartile range in the X axis   
fBodyGyro.iqr.Y      
   --  FFT body gyroscope interquartile range in the Y axis   
fBodyGyro.iqr.Z      
   --  FFT body gyroscope interquartile range in the Z axis   
fBodyGyro.entropy.X      
   --  FFT body gyroscope signal entropy in the X axis   
fBodyGyro.entropy.Y      
   --  FFT body gyroscope signal entropy in the Y axis   
fBodyGyro.entropy.Z      
   --  FFT body gyroscope signal entropy in the Z axis   
fBodyGyro.maxInds.X      
   --  FFT body gyroscope -maxIndsin the X axis   
fBodyGyro.maxInds.Y      
   --  FFT body gyroscope -maxIndsin the Y axis   
fBodyGyro.maxInds.Z      
   --  FFT body gyroscope -maxIndsin the Z axis   
fBodyGyro.meanFreq.X         
   --  FFT body gyroscope weighted average of the frequency components in the X axis   
fBodyGyro.meanFreq.Y         
   --  FFT body gyroscope weighted average of the frequency components in the Y axis   
fBodyGyro.meanFreq.Z         
   --  FFT body gyroscope weighted average of the frequency components in the Z axis   
fBodyGyro.skewness.X         
   --  FFT body gyroscope skewness of the frequency domain signal in the X axis   
fBodyGyro.kurtosis.X         
   --  FFT body gyroscope kurtosis of the frequency domain signal in the X axis   
fBodyGyro.skewness.Y         
   --  FFT body gyroscope skewness of the frequency domain signal in the Y axis   
fBodyGyro.kurtosis.Y         
   --  FFT body gyroscope kurtosis of the frequency domain signal in the Y axis   
fBodyGyro.skewness.Z         
   --  FFT body gyroscope skewness of the frequency domain signal in the Z axis   
fBodyGyro.kurtosis.Z         
   --  FFT body gyroscope kurtosis of the frequency domain signal in the Z axis   
fBodyGyro.bandsEnergy.1.8        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -1,8   
fBodyGyro.bandsEnergy.9.16       
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -9,16   
fBodyGyro.bandsEnergy.17.24      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -17,24   
fBodyGyro.bandsEnergy.25.32      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -25,32   
fBodyGyro.bandsEnergy.33.40      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -33,40   
fBodyGyro.bandsEnergy.41.48      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -41,48   
fBodyGyro.bandsEnergy.49.56      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -49,56   
fBodyGyro.bandsEnergy.57.64      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -57,64   
fBodyGyro.bandsEnergy.1.16       
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -1,16   
fBodyGyro.bandsEnergy.17.32      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -17,32   
fBodyGyro.bandsEnergy.33.48      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -33,48   
fBodyGyro.bandsEnergy.49.64      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -49,64   
fBodyGyro.bandsEnergy.1.24       
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -1,24   
fBodyGyro.bandsEnergy.25.48      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -25,48   
fBodyGyro.bandsEnergy.1.8.1      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -1,8   
fBodyGyro.bandsEnergy.9.16.1         
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -9,16   
fBodyGyro.bandsEnergy.17.24.1        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -17,24   
fBodyGyro.bandsEnergy.25.32.1        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -25,32   
fBodyGyro.bandsEnergy.33.40.1        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -33,40   
fBodyGyro.bandsEnergy.41.48.1        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -41,48   
fBodyGyro.bandsEnergy.49.56.1        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -49,56   
fBodyGyro.bandsEnergy.57.64.1        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -57,64   
fBodyGyro.bandsEnergy.1.16.1         
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -1,16   
fBodyGyro.bandsEnergy.17.32.1        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -17,32   
fBodyGyro.bandsEnergy.33.48.1        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -33,48   
fBodyGyro.bandsEnergy.49.64.1        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -49,64   
fBodyGyro.bandsEnergy.1.24.1         
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -1,24   
fBodyGyro.bandsEnergy.25.48.1        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -25,48   
fBodyGyro.bandsEnergy.1.8.2      
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -1,8   
fBodyGyro.bandsEnergy.9.16.2         
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -9,16   
fBodyGyro.bandsEnergy.17.24.2        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -17,24   
fBodyGyro.bandsEnergy.25.32.2        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -25,32   
fBodyGyro.bandsEnergy.33.40.2        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -33,40   
fBodyGyro.bandsEnergy.41.48.2        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -41,48   
fBodyGyro.bandsEnergy.49.56.2        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -49,56   
fBodyGyro.bandsEnergy.57.64.2        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -57,64   
fBodyGyro.bandsEnergy.1.16.2         
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -1,16   
fBodyGyro.bandsEnergy.17.32.2        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -17,32   
fBodyGyro.bandsEnergy.33.48.2        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -33,48   
fBodyGyro.bandsEnergy.49.64.2        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -49,64   
fBodyGyro.bandsEnergy.1.24.2         
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -1,24   
fBodyGyro.bandsEnergy.25.48.2        
   --  FFT body gyroscope energy of a frequency interval within 64 bins of the FFT -25,48   
fBodyAccMag.mean         
   --  FFT body accelerometer Magmean value    
fBodyAccMag.std      
   --  FFT body accelerometer Magstandard deviation    
fBodyAccMag.mad      
   --  FFT body accelerometer Magmedian absolute deviation   
fBodyAccMag.max      
   --  FFT body accelerometer Magmaximum value    
fBodyAccMag.min      
   --  FFT body accelerometer Magminimum value    
fBodyAccMag.sma      
   --  FFT body accelerometer Magsignal magnitude area   
fBodyAccMag.energy       
   --  FFT body accelerometer Magenergy measure    
fBodyAccMag.iqr      
   --  FFT body accelerometer Maginterquartile range    
fBodyAccMag.entropy      
   --  FFT body accelerometer Magsignal entropy    
fBodyAccMag.maxInds      
   --  FFT body accelerometer Mag-maxInds   
fBodyAccMag.meanFreq         
   --  FFT body accelerometer Magweighted average of the frequency components    
fBodyAccMag.skewness         
   --  FFT body accelerometer Magskewness of the frequency domain signal    
fBodyAccMag.kurtosis         
   --  FFT body accelerometer Magkurtosis of the frequency domain signal    
fBodyBodyAccJerkMag.mean         
   --  FFT body body accelerometer JerkMagmean value    
fBodyBodyAccJerkMag.std      
   --  FFT body body accelerometer JerkMagstandard deviation    
fBodyBodyAccJerkMag.mad      
   --  FFT body body accelerometer JerkMagmedian absolute deviation   
fBodyBodyAccJerkMag.max      
   --  FFT body body accelerometer JerkMagmaximum value    
fBodyBodyAccJerkMag.min      
   --  FFT body body accelerometer JerkMagminimum value    
fBodyBodyAccJerkMag.sma      
   --  FFT body body accelerometer JerkMagsignal magnitude area   
fBodyBodyAccJerkMag.energy       
   --  FFT body body accelerometer JerkMagenergy measure    
fBodyBodyAccJerkMag.iqr      
   --  FFT body body accelerometer JerkMaginterquartile range    
fBodyBodyAccJerkMag.entropy      
   --  FFT body body accelerometer JerkMagsignal entropy    
fBodyBodyAccJerkMag.maxInds      
   --  FFT body body accelerometer JerkMag-maxInds   
fBodyBodyAccJerkMag.meanFreq         
   --  FFT body body accelerometer JerkMagweighted average of the frequency components    
fBodyBodyAccJerkMag.skewness         
   --  FFT body body accelerometer JerkMagskewness of the frequency domain signal    
fBodyBodyAccJerkMag.kurtosis         
   --  FFT body body accelerometer JerkMagkurtosis of the frequency domain signal    
fBodyBodyGyroMag.mean        
   --  FFT body body gyroscope Magmean value    
fBodyBodyGyroMag.std         
   --  FFT body body gyroscope Magstandard deviation    
fBodyBodyGyroMag.mad         
   --  FFT body body gyroscope Magmedian absolute deviation   
fBodyBodyGyroMag.max         
   --  FFT body body gyroscope Magmaximum value    
fBodyBodyGyroMag.min         
   --  FFT body body gyroscope Magminimum value    
fBodyBodyGyroMag.sma         
   --  FFT body body gyroscope Magsignal magnitude area   
fBodyBodyGyroMag.energy      
   --  FFT body body gyroscope Magenergy measure    
fBodyBodyGyroMag.iqr         
   --  FFT body body gyroscope Maginterquartile range    
fBodyBodyGyroMag.entropy         
   --  FFT body body gyroscope Magsignal entropy    
fBodyBodyGyroMag.maxInds         
   --  FFT body body gyroscope Mag-maxInds   
fBodyBodyGyroMag.meanFreq        
   --  FFT body body gyroscope Magweighted average of the frequency components    
fBodyBodyGyroMag.skewness        
   --  FFT body body gyroscope Magskewness of the frequency domain signal    
fBodyBodyGyroMag.kurtosis        
   --  FFT body body gyroscope Magkurtosis of the frequency domain signal    
fBodyBodyGyroJerkMag.mean        
   --  FFT body body gyroscope JerkMagmean value    
fBodyBodyGyroJerkMag.std         
   --  FFT body body gyroscope JerkMagstandard deviation    
fBodyBodyGyroJerkMag.mad         
   --  FFT body body gyroscope JerkMagmedian absolute deviation   
fBodyBodyGyroJerkMag.max         
   --  FFT body body gyroscope JerkMagmaximum value    
fBodyBodyGyroJerkMag.min         
   --  FFT body body gyroscope JerkMagminimum value    
fBodyBodyGyroJerkMag.sma         
   --  FFT body body gyroscope JerkMagsignal magnitude area   
fBodyBodyGyroJerkMag.energy      
   --  FFT body body gyroscope JerkMagenergy measure    
fBodyBodyGyroJerkMag.iqr         
   --  FFT body body gyroscope JerkMaginterquartile range    
fBodyBodyGyroJerkMag.entropy         
   --  FFT body body gyroscope JerkMagsignal entropy    
fBodyBodyGyroJerkMag.maxInds         
   --  FFT body body gyroscope JerkMag-maxInds   
fBodyBodyGyroJerkMag.meanFreq        
   --  FFT body body gyroscope JerkMagweighted average of the frequency components    
fBodyBodyGyroJerkMag.skewness        
   --  FFT body body gyroscope JerkMagskewness of the frequency domain signal    
fBodyBodyGyroJerkMag.kurtosis        
   --  FFT body body gyroscope JerkMagkurtosis of the frequency domain signal    
angletBodyAccMean.gravity        
   --  angle(Time domain body accelerometer Mean,gravity)   
angletBodyAccJerkMean.gravityMean        
   --  angle(Time domain body accelerometer JerkMean),gravityMean)   
angletBodyGyroMean.gravityMean       
   --  angle(Time domain body gyroscope Mean,gravityMean)   
angletBodyGyroJerkMean.gravityMean       
   --  angle(Time domain body gyroscope JerkMean,gravityMean)   
angleX.gravityMean       
   --  angle(X,gravityMean)   
angleY.gravityMean       
   --  angle(Y,gravityMean)   
angleZ.gravityMean       
   --  angle(Z,gravityMean)   

###tidyData CodeBook

These are the columns within the final data set **tidyData**. The prefix "avg." was affixed to those columns that were selected from the original data since these columns now contain averages of the original data by subject and activity.  

subject --   
   Participant identifier, 1...30  
activity --   
   Type of activity, factor with six levels, see activity_labels.txt
avg.tBodyAcc.mean.X --  
  Average of time domain body accelerometer mean in the X axis  
avg.tBodyAcc.mean.Y --  
  Average of time domain body accelerometer mean in the Y axis  
avg.tBodyAcc.mean.Z --  
  Average of time domain body accelerometer mean in the z axis  
avg.tBodyAcc.std.X  --  
  Average of time domain body accelerometer .std.X
avg.tBodyAcc.std.Y  --  
  Average of time domain body accelerometer .std.Y
avg.tBodyAcc.std.Z  --  
  Average of time domain body accelerometer .std.Z
avg.tGravityAcc.mean.X  --  
  Average of time domain gravity accelerometer mean in the X axis  
avg.tGravityAcc.mean.Y  --  
  Average of time domain gravity accelerometer mean in the Y axis  
avg.tGravityAcc.mean.Z  --  
  Average of time domain gravity accelerometer mean in the z axis  
avg.tGravityAcc.std.X   --  
  Average of time domain gravity accelerometer .std.X
avg.tGravityAcc.std.Y   --  
  Average of time domain gravity accelerometer .std.Y
avg.tGravityAcc.std.Z   --  
  Average of time domain gravity accelerometer .std.Z
avg.tBodyAccJerk.mean.X --  
  Average of time domain body accelerometer Jerkmean in the X axis  
avg.tBodyAccJerk.mean.Y --  
  Average of time domain body accelerometer Jerkmean in the Y axis  
avg.tBodyAccJerk.mean.Z --  
  Average of time domain body accelerometer Jerkmean in the z axis  
avg.tBodyAccJerk.std.X  --  
  Average of time domain body accelerometer Jerk.std.X
avg.tBodyAccJerk.std.Y  --  
  Average of time domain body accelerometer Jerk.std.Y
avg.tBodyAccJerk.std.Z  --  
  Average of time domain body accelerometer Jerk.std.Z
avg.tBodyGyro.mean.X    --  
  Average of time domain body gyroscope mean in the X axis  
avg.tBodyGyro.mean.Y    --  
  Average of time domain body gyroscope mean in the Y axis  
avg.tBodyGyro.mean.Z    --  
  Average of time domain body gyroscope mean in the z axis  
avg.tBodyGyro.std.X --  
  Average of time domain body gyroscope .std.X
avg.tBodyGyro.std.Y --  
  Average of time domain body gyroscope .std.Y
avg.tBodyGyro.std.Z --  
  Average of time domain body gyroscope .std.Z
avg.tBodyGyroJerk.mean.X    --  
  Average of time domain body gyroscope Jerkmean in the X axis  
avg.tBodyGyroJerk.mean.Y    --  
  Average of time domain body gyroscope Jerkmean in the Y axis  
avg.tBodyGyroJerk.mean.Z    --  
  Average of time domain body gyroscope Jerkmean in the z axis  
avg.tBodyGyroJerk.std.X --  
  Average of time domain body gyroscope Jerk.std.X
avg.tBodyGyroJerk.std.Y --  
  Average of time domain body gyroscope Jerk.std.Y
avg.tBodyGyroJerk.std.Z --  
  Average of time domain body gyroscope Jerk.std.Z
avg.tBodyAccMag.mean    --  
  Average of time domain body accelerometer Mag.mean
avg.tBodyAccMag.std --  
  Average of time domain body accelerometer Mag.std
avg.tGravityAccMag.mean --  
  Average of time domain gravity accelerometer Mag.mean
avg.tGravityAccMag.std  --  
  Average of time domain gravity accelerometer Mag.std
avg.tBodyAccJerkMag.mean    --  
  Average of time domain body accelerometer JerkMag.mean
avg.tBodyAccJerkMag.std --  
  Average of time domain body accelerometer JerkMag.std
avg.tBodyGyroMag.mean   --  
  Average of time domain body gyroscope Mag.mean
avg.tBodyGyroMag.std    --  
  Average of time domain body gyroscope Mag.std
avg.tBodyGyroJerkMag.mean   --  
  Average of time domain body gyroscope JerkMag.mean
avg.tBodyGyroJerkMag.std    --  
  Average of time domain body gyroscope JerkMag.std
avg.fBodyAcc.mean.X --  
  Average of .fBodyAccmean in the X axis  
avg.fBodyAcc.mean.Y --  
  Average of .fBodyAccmean in the Y axis  
avg.fBodyAcc.mean.Z --  
  Average of .fBodyAccmean in the z axis  
avg.fBodyAcc.std.X  --  
  Average of .fBodyAcc.std.X
avg.fBodyAcc.std.Y  --  
  Average of .fBodyAcc.std.Y
avg.fBodyAcc.std.Z  --  
  Average of .fBodyAcc.std.Z
avg.fBodyAcc.meanFreq.X --  
  Average of .fBodyAcc.meanFreq.X
avg.fBodyAcc.meanFreq.Y --  
  Average of .fBodyAcc.meanFreq.Y
avg.fBodyAcc.meanFreq.Z --  
  Average of .fBodyAcc.meanFreq.Z
avg.fBodyAccJerk.mean.X --  
  Average of .fBodyAccJerkmean in the X axis  
avg.fBodyAccJerk.mean.Y --  
  Average of .fBodyAccJerkmean in the Y axis  
avg.fBodyAccJerk.mean.Z --  
  Average of .fBodyAccJerkmean in the z axis  
avg.fBodyAccJerk.std.X  --  
  Average of .fBodyAccJerk.std.X
avg.fBodyAccJerk.std.Y  --  
  Average of .fBodyAccJerk.std.Y
avg.fBodyAccJerk.std.Z  --  
  Average of .fBodyAccJerk.std.Z
avg.fBodyAccJerk.meanFreq.X --  
  Average of .fBodyAccJerk.meanFreq.X
avg.fBodyAccJerk.meanFreq.Y --  
  Average of .fBodyAccJerk.meanFreq.Y
avg.fBodyAccJerk.meanFreq.Z --  
  Average of .fBodyAccJerk.meanFreq.Z
avg.fBodyGyro.mean.X    --  
  Average of .fBodyGyromean in the X axis  
avg.fBodyGyro.mean.Y    --  
  Average of .fBodyGyromean in the Y axis  
avg.fBodyGyro.mean.Z    --  
  Average of .fBodyGyromean in the z axis  
avg.fBodyGyro.std.X --  
  Average of .fBodyGyro.std.X
avg.fBodyGyro.std.Y --  
  Average of .fBodyGyro.std.Y
avg.fBodyGyro.std.Z --  
  Average of .fBodyGyro.std.Z
avg.fBodyGyro.meanFreq.X    --  
  Average of .fBodyGyro.meanFreq.X
avg.fBodyGyro.meanFreq.Y    --  
  Average of .fBodyGyro.meanFreq.Y
avg.fBodyGyro.meanFreq.Z    --  
  Average of .fBodyGyro.meanFreq.Z
avg.fBodyAccMag.mean    --  
  Average of .fBodyAccMag.mean
avg.fBodyAccMag.std --  
  Average of .fBodyAccMag.std
avg.fBodyAccMag.meanFreq    --  
  Average of .fBodyAccMag.meanFreq
avg.fBodyBodyAccJerkMag.mean    --  
  Average of .fBodyBodyAccJerkMag.mean
avg.fBodyBodyAccJerkMag.std --  
  Average of .fBodyBodyAccJerkMag.std
avg.fBodyBodyAccJerkMag.meanFreq    --  
  Average of .fBodyBodyAccJerkMag.meanFreq
avg.fBodyBodyGyroMag.mean   --  
  Average of .fBodyBodyGyroMag.mean
avg.fBodyBodyGyroMag.std    --  
  Average of .fBodyBodyGyroMag.std
avg.fBodyBodyGyroMag.meanFreq   --  
  Average of .fBodyBodyGyroMag.meanFreq
avg.fBodyBodyGyroJerkMag.mean   --  
  Average of .fBodyBodyGyroJerkMag.mean
avg.fBodyBodyGyroJerkMag.std    --  
  Average of .fBodyBodyGyroJerkMag.std
avg.fBodyBodyGyroJerkMag.meanFreq   --  
  Average of .fBodyBodyGyroJerkMag.meanFreq
avg.angletBodyAccMean.gravity   --  
  Average of .angltime domain body accelerometer Mean.gravity
avg.angletBodyAccJerkMean.gravityMean   --  
  Average of .angltime domain body accelerometer JerkMean.gravityMean
avg.angletBodyGyroMean.gravityMean  --  
  Average of .angltime domain body gyroscope Mean.gravityMean
avg.angletBodyGyroJerkMean.gravityMean  --  
  Average of .angltime domain body gyroscope JerkMean.gravityMean
avg.angleX.gravityMean  --  
  Average of .angleX.gravityMean
avg.angleY.gravityMean  --  
  Average of .angleY.gravityMean
avg.angleZ.gravityMean  --  
  Average of .angleZ.gravityMean
     

## Transformations

The **features.txt** file was read and the result was a data frame of column names. This was edited to standarize appearance as noted above.

The **activity_labels.txt** file was read into the data frame **activities**.

The testing and training data were acquired in separate operations. First, subject and activity information was for the type of activity was read into separate data frames (**test_subjects** and **test_activity**). Then the data was read. The three data frames one were then combined using cbind. At this time a new column, **type**, was also introduced to distinguish between "test" and "train" sets when all the data was eventually combined. Column names were added using the **features** data frame as the column names. This resulted in the data frame **test_complete**.The process was repeated for the training data.

rbind was then used to combine the test and training data into one dataset, **completeData**.

The **activities** data frame was then used to convert the column **activity** in **completeData** from an integer to a factor, providing text descriptions of each type of activity.

A select command was then used to extract columns of interest, which were **subject**, **activity** and any column containing either "mean" or "std", and stored in **subsetData**.

**subsetData** was then grouped by **subject** and **activity** and the summarize_each command was used to compute the mean of all the columns containing mean or standard deviation data. The result was stored in the data frame **tidyData**.

This column names that had been computed were then prefixed with "avg." to indicate that the information represented the mean of the original data.

**tidyData** was then written to a file using write.table .

**tidyData** can be read using the following statement:
'''{R}
tidyData <- read.table(filename, header = TRUE)  
'''