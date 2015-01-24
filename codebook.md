# Code book

The tidy data can be read into R with the following code:
read.table("tidy_data_set.txt", header=TRUE)

The [tidy_data_set.txt](../tidy_data_set.txt) file in this directory is a tidy subset of the data provided in the Human Activity Recognition Using Smartphones Data Set. The source data is available from http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones# and it's also included in the UCI HAR Dataset directory in this repo. 

tidy_data_set.txt includes the combined test and training data sets from the following files:

- [UCI HAR Dataset/test/subject_test.txt](./UCI HAR Dataset/test/subject_test.txt)
- [UCI HAR Dataset/test/X_test.txt](./UCI HAR Dataset/test/X_test.txt)
- [UCI HAR Dataset/test/Y_test.txt](./UCI HAR Dataset/test/Y_test.txt)
- [UCI HAR Dataset/train/subject_train.txt](./UCI HAR Dataset/train/subject_train.txt)
- [UCI HAR Dataset/train/X_train.txt](./UCI HAR Dataset/train/X_train.txt)
- [UCI HAR Dataset/train/Y_train.txt](./UCI HAR Dataset/train/Y_train.txt)

 In the tidy data set, the values in the subject_test and subject_train files are combined to create a single TestSubject column that identifies the study participant, the values in the Y_test and Y_train data are combined to create a single Activity column that indicates that activity class (for instance, walking or sitting), and the values in the X_test and X_train files are combined to create additional variable columns, one column for each measurement and calculation included in the data set (561 variable columns total, in the initial combined data set; 563 columns including the TestSubject and Activity columns).

The tidy data set is a subset of this combined data that includes only measurements on the mean and standard deviation for each measure. This reduces the data to 638 columns (68 feature variable measurements, plus the TestSubject and Activity columns)

The size of the tidy data set was further reduced by averaging each variable for each activity and each subject. This resulted in 180 rows of data, with a unique combination of TestSubject and Activity values in each row. 

I updated the feature variable names in the tidy data to make it easier for readers and consumers of the data to understand the measurement of each column. The naming follows the following convention:




1) Describe the tidy data set, including variables and units
2) Describe the summary choices you made

