GettingAndCleaningData_Project
==============================

#Data Source

Original data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
Description of the original dataset: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

#Provided files

'train/X_train.txt': Training set.

'train/y_train.txt': Training labels.

'test/X_test.txt': Test set.

'test/y_test.txt': Test labels.

'README.txt'

'features_info.txt': Information about feature variables.

'features.txt': Feature list.

'activity_labels.txt': Activity labels and activity names.



#Transformation tasks

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names. 
5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject. 


#Approach for getting a tidy dataset

The code for cleaning the motion data provided by UCI is split up in 5 steps. I changed the order of the original 5 steps and added the fourth step from the assignment before the second step, naminng the columns and thus giving variable names to the measurements.

First, the raw files for the test and training set as well as the corresponding activity labels and subject IDs are read into R and subsequently collapsed into one dataset by using cbind and rbind. A tidy dataset contains all the data in one file or one complete dataset instead of distributing it across various ones.

In the second step, the feature variables are loaded into R and then edited to be in a tidy format by removing parentheses, dashes and commas using the R function gsub. In the next step, they are added as column names to the dataset that was produced in the first step with the names R function. Tidy variables don't contain characters that are also metadata characters for regex expressions.

Third, the variables are reduced to those only containing the mean and the standard deviation for each measurement type. All the other variables are deleted. A tidy dataset contains the information you are interested in and excludes additional information that is not related to the research question and won't improve understanding of if.

Fourth, the variable Activity is edited from displaying numbers to displaying the activity name instead. A tidy dataset is a dataset that is easily understood and self-explanatory. Names/Descriptions are thus prefered to numbered variables for qualitative variables.


In the last step a new dataset is generated and saved as TidyDataSet.txt which includes the averages of each variable for each activity and each subject using the R functions aggregate and write.table. The last step summarizes the data and is now ready to be analyzed.
