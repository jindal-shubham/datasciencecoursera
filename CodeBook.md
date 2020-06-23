    1. Download the dataset in the folder UCI HAR Dataset

    2. Assign each data to variables
        features <- features.txt : 561 rows, 2 columns
        activities <- activity_labels.txt : 6 rows, 2 columns
        subject_test <- test/subject_test.txt : 2947 rows, 1 column
        x_test <- test/X_test.txt : 2947 rows, 561 columns
        y_test <- test/y_test.txt : 2947 rows, 1 columns
        subject_train <- test/subject_train.txt : 7352 rows, 1 column
        x_train <- test/X_train.txt : 7352 rows, 561 columns
        y_train <- test/y_train.txt : 7352 rows, 1 columns

   3. Merge the training and the test sets to create one data set
        X is created by merging x_train and x_test using rbind()
        Y is created by merging y_train and y_test using rbind()
        Subject is created by merging subject_train and subject_test using rbind()
        Merged_Data is created by merging Subject, Y and X using cbind() function. It has 10299 rows and 563 columns.

   4. Extracts only the measurements on the mean and standard deviation for each measurement
        TidyData is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation for each measurement. It has 88 olumns left.

    5. Uses descriptive activity names to name the activities in the data set
        Numbers in code column of the TidyData are replaced by corresponding activity taken from second column of the activities variable

    6. Appropriately labels the data set with descriptive variable names
        code column in TidyData renamed into activities
        All Acc in column’s name replaced by Accelerometer
        All Gyro in column’s name replaced by Gyroscope
        All BodyBody in column’s name replaced by Body
        All Mag in column’s name replaced by Magnitude
        All start with character f in column’s name replaced by Frequency
        All start with character t in column’s name replaced by Time

    7. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
        FinalData is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
