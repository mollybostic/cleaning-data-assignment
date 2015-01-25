# Code book

The tidy data in [tidy_data_set.txt](./tidy_data_set.txt) can be read into R with the following code:
	read.table("tidy_data_set.txt", header=TRUE, colClasses=c('factor', 'factor', rep('numeric', 66)))

## Description of the tidy data set

The [tidy_data_set.txt](./tidy_data_set.txt) file in this directory is a tidy subset of the data provided in the Human Activity Recognition Using Smartphones Data Set. The source data is available from http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones# and it's also included in the UCI HAR Dataset directory in this repo. 

tidy_data_set.txt includes the combined test and training data sets from the following files:

- [UCI HAR Dataset/test/subject_test.txt](./UCI HAR Dataset/test/subject_test.txt)
- [UCI HAR Dataset/test/X_test.txt](./UCI HAR Dataset/test/X_test.txt)
- [UCI HAR Dataset/test/y_test.txt](./UCI HAR Dataset/test/y_test.txt)
- [UCI HAR Dataset/train/subject_train.txt](./UCI HAR Dataset/train/subject_train.txt)
- [UCI HAR Dataset/train/X_train.txt](./UCI HAR Dataset/train/X_train.txt)
- [UCI HAR Dataset/train/y_train.txt](./UCI HAR Dataset/train/y_train.txt)

In the tidy data set, the values in the subject_test and subject_train files are combined to create a single TestSubject column that identifies the study participant, the values in the Y_test and Y_train data are combined to create a single Activity column that indicates that activity class (for instance, walking or sitting), and the values in the X_test and X_train files are combined to create additional variable columns, one column for each measurement and calculation included in the data set (561 variable columns total, in the initial combined data set; 563 columns including the TestSubject and Activity columns).

The tidy data set is a subset of this combined data that includes only measurements on the mean and standard deviation for each measure. This reduces the data to 638 columns (68 feature variable measurements, plus the TestSubject and Activity columns)

The size of the tidy data set was further reduced by averaging each variable for each activity and each subject. This resulted in 180 rows of data, with a unique combination of TestSubject and Activity values in each row. 

There are some interesting threads on the course discussion board about wide vs. narrow formats for tidy data. I chose to use the wide format, aligning to these principles:

1. Each column represents a variable or measure or characteristic.
2. Each variable is in one column.
3. Each observation of the variable is in a different row.

Hence the final tidy data set is 180 rows x 68 columns.

## Description of variables

I updated the feature variable names in the tidy data to make it easier for readers and consumers of the data to understand the measurement of each column. The names use the following convention:

- The first word(s) indicates the type of metric, **Mean** or **StandardDeviation**
- Next, **FFT** is included, if applicable, to indicate that the measurement had a Fast Fourier Transform (FFT) applied. 
- Either **Body** or **Gravity** is included to indicate the type of signal
- Either **Acceleration** or **AngularVelocity** is included to indicate the type of measurement. I replaced "Gyro" with "AngularVelocity" since that's what the gyroscope is measuring.
- **Jerk** indicates a measure where the body linear acceleration and angular velocity were derived in time to obtain Jerk signals
- **Magnitude** indicates a magnitude calculation
- **XAxis**, **YAxis**, and **ZAxis** indicate a measurement for the X, Y, or Z axis.

Here are some example mappings of old to new column names:

- Old: tBodyAcc-mean()-X
- New: MeanBodyAccelerationXAxis

- Old: tGravityAcc-std()-Y
- New: StandarddeviationGravityAccelerationYAxis

- Old: fBodyGyroMag-std()
- New: StandardDeviationFFTBodyAngularVelocityMagnitude

The overall result is that the names are long but hopefully easier to understand.

## Description of run_analysis.R script

[README.md](./README.md) contains a walkthrough of the [run_analysis.R](./run_analysis.R) script and notes about how to run the script.
