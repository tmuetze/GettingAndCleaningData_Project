GettingAndCleaningData_Project
==============================
The code for cleaning the motion data provided by UCI is split up in 4 steps:

First, the raw files for the test and training set as well as the corresponding activity labels and subject IDs are read into R and subsequently collapsed into one dataset by using cbind and rbind.

In the second step, the feature variables are loaded into R and then edited to be in a tidy format by removing parentheses, dashes and commas using the R function gsub. In the next step, they are added as column names to the dataset that was produced in the first step with the names R function.

Third, the variable Activity is edited from displaying numbers to displaying the activity name instead - for easier understandability.

In the last step a new dataset is generated and saved as TidyDataSet.txt which includes the averages of each variable for each activity and each subject using the R functions aggregate and write.table.
