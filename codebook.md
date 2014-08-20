Code Book
================================================================

#Feature List

Subject	- field width: 2, a number corresponding to each participating person,  range: 1-30  

Activity - field width: 18, activity types, range:1 WALKING, 2 WALKING_UPSTAIRS, 3 WALKING_DOWNSTAIRS, 4 SITTING, 5 STANDING, 6 LAYING   

tBodyAccmeanX	- field width: 18, Time domain body acceleration mean along X, range: 1-30 

tBodyAccmeanY	- field width: 18, Time domain body acceleration mean along Y, range: 1-30 

tBodyAccmeanZ	- field width: 18, Time domain body acceleration mean along Z, range: 1-30 

tBodyAccstdX - field width: 18, Time domain body acceleration standard deviation along X, range: 1-30 

tBodyAccstdY - field width: 18, Time domain body acceleration standard deviation along Y, range: 1-30 
	
tBodyAccstdZ - field width: 18, Time domain body acceleration standard deviation along Z, range: 1-30 
	
tGravityAccmeanX - field width: 18, Time domain gravity acceleration mean along X, range: 1-30 
		
tGravityAccmeanY - field width: 18, Time domain gravity acceleration mean along Y, range: 1-30 

tGravityAccmeanZ - field width: 18, Time domain gravity acceleration mean along Z, range: 1-30 	

tGravityAccstdX	 
tGravityAccstdY	 
tGravityAccstdZ	 
tBodyAccJerkmeanX	
tBodyAccJerkmeanY	
tBodyAccJerkmeanZ	
tBodyAccJerkstdX	
tBodyAccJerkstdY	
tBodyAccJerkstdZ	
tBodyGyromeanX	
tBodyGyromeanY	
tBodyGyromeanZ	
tBodyGyrostdX	
tBodyGyrostdY	
tBodyGyrostdZ	
tBodyGyroJerkmeanX 	
tBodyGyroJerkmeanY 	
tBodyGyroJerkmeanZ 	
tBodyGyroJerkstdX	
tBodyGyroJerkstdY	
tBodyGyroJerkstdZ	
tBodyAccMagstd	
tGravityAccMagstd	
tBodyAccJerkMagstd	
tBodyGyroMagstd	 
tBodyGyroJerkMagstd	 
fBodyAccmeanX	 
fBodyAccmeanY	 
fBodyAccmeanZ	
fBodyAccstdX	
fBodyAccstdY	
fBodyAccstdZ	
fBodyAccJerkmeanX	
fBodyAccJerkmeanY	
fBodyAccJerkmeanZ	
fBodyAccJerkstdX	
fBodyAccJerkstdY	
fBodyAccJerkstdZ	
fBodyGyromeanX	
fBodyGyromeanY	
fBodyGyromeanZ	
fBodyGyrostdX	
fBodyGyrostdY	
fBodyGyrostdZ	
fBodyAccMagstd	
fBodyBodyAccJerkMagstd	 
fBodyBodyGyroMagstd  
fBodyBodyGyroJerkMagstd  



#Approach
The following text is adopted from the original file "features_info.txt".

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz.

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 

These signals were used to estimate variables of the feature vector for each pattern:  

'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.


tBodyAcc-XYZ
tGravityAcc-XYZ
tBodyAccJerk-XYZ
tBodyGyro-XYZ
tBodyGyroJerk-XYZ
tBodyAccMag
tGravityAccMag
tBodyAccJerkMag
tBodyGyroMag
tBodyGyroJerkMag
fBodyAcc-XYZ
fBodyAccJerk-XYZ
fBodyGyro-XYZ
fBodyAccMag
fBodyAccJerkMag
fBodyGyroMag
fBodyGyroJerkMag


The set of variables that were estimated from these signals are:

mean(): Mean value

std(): Standard deviation

In the last step the mean was taken over each variable by each subject and each activity.
