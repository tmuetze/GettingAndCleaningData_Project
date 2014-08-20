GettingAndCleaningData_Project
==============================
The code for cleaning the motion data provided by 
###1 Merges the training and the test sets to create one data set.
setwd("./UCI HAR Dataset")
#loading the test set into R
tbl <- read.table("test/X_test.txt")

#loading the label for the test set into R
labl <- read.table("test/y_test.txt")

#loading the subject data
subj <- read.table("test/subject_test.txt")

#adding the subject and label in front of the test set
testSet <- cbind(subj, labl,tbl)

#loading the training set
tbl2 <- read.table("train/X_train.txt")

#loading the label for the training set into R
labl2 <- read.table("train/y_train.txt")

#loading the subject data
subj2 <- read.table("train/subject_train.txt")

#adding the subject and label in front of the training set
trainSet <- cbind(subj2, labl2,tbl2)


## merge training set and test set to one table
merged <- rbind(trainSet, testSet)

#-------------------------------------------------------------------------------
###2 Extracts only the measurements on the mean and standard
###   deviation for each measurement. 

# load features.txt into R which desribes the columns
features <- read.table("features.txt")
featureL <- as.character(factor(features[,2]))
featureLi <- gsub("\\(|-|\\)","", featureL)
featureList <- gsub(",","", featureLi)

#name each column of the test set with the help of features_info.txt (provided)
names(merged) <- c("Subject", "Activity",featureList)

#select features for mean and std for each measurement
selcFeatures <- grep("mean+[^F]|std", featureList) + 2

#reduce columns of the merged dataset to the ones needed (i.e. the selcFeatures)
newdataset <- merged[c(1,2,selcFeatures)]


#-------------------------------------------------------------------------------
#3 Uses descriptive activity names to name the activities in the data set

#loading activity labels into R
activityLabels <- read.table("activity_labels.txt")

#assign activity words to numbers as a factor
newdataset$Activity <- factor(newdataset$Activity, labels=activityLabels[,2])


#-------------------------------------------------------------------------------
#4 Appropriately labels the data set with descriptive variable names. 
#done in # 2


#-------------------------------------------------------------------------------
#5 Creates a second, independent tidy data set with the average of each
#   variable for each activity and each subject.

# average across activities and subjects
dim(newdataset)
data2 <-aggregate(newdataset[,3:59], by=list("Subject"=newdataset$Subject, "Activity"=newdataset$Activity), FUN=mean)
data2[1:5,1:5]
write.table(data2, file = "TidyDataSet.txt", row.name=FALSE)
