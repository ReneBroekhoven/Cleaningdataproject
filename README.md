---
title: "Cleaning Data Project"
author: "Rene Broekhoven"
date: "Thursday, July 23, 2015"
output: html_document
---

The datafile for this project can be obtained at : 

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

This is a ZIP-file which you should unzip with your own tools (Windows or Mac) in a directory of your choosing.
For example : c:/desktop/project
After unzipping, you will get a folder "getdata-projectfiles-UCI HAR Dataset".
In this folder you will find "UCI HAR Dataset" : this directory will be your starting point.
This script can be executed from the original directory (in this example : c:/desktop/project)


```{r}

## Unzipping the dataset will get you the directory :  getdata-projectfiles-UCI HAR Dataset
## The starting workingdirectory will be set to the subdirectory herein : "........./"UCI HAR Dataset/"

## Cleaning everything and setting the working directory ##
rm(list=ls())
startwd <- getwd()


## !! Change the dots(....) to your directory where you unzipped the UCI HAR dataset.
## After the unzipping, there should be the folder :  "getdata-projectfiles-UCI HAR Dataset"
## This example is my own directory I used :
##      EXAMPLE : my_unzip_dir <- "c:/users/rene/desktop/cleaningdata/project/"
my_unzip_dir <- "...."


# setting the working directory
project_working_dir <- "getdata-projectfiles-UCI HAR Dataset/UCI HAR Dataset"
setwd(paste(my_unzip_dir,project_working_dir, sep=""))

#using library(plyr) to make things easy
library(dplyr)

## QUESTION 1 ##

# Making dataframe's and merging
test_df <- read.table("./test/X_test.txt")
train_df <- read.table("./train/X_train.txt")
my_df <- rbind(train_df, test_df)

## QUESTION 2 ##

# Getting only the mean en std variables
# First getting the names from the file features.txt
features <- read.table("features.txt")
features <- as.character(features[,2])
colnames(my_df) <- features

# to remove the duplicates (although I could nog find them by hand...)
my_df <- my_df[ , !duplicated(colnames(my_df))]

# selecting the right columns with a simle regular expression
# I also deleted the variables with meanFreq, because they seem to be derived variables asnd therefore untidy
my_df <- select(my_df, matches("mean|std"))  # as requested in the project
my_df <- select(my_df,-matches("meanFreq"))  # my interpretation ! : these are derived variables (= 'untidy')

# adding the activity and subject columns from train and test (the columns now are called V1 and V2)
test_activity  <- read.table("./test/y_test.txt")
test_subject   <- read.table("./test/subject_test.txt")
train_activity <- read.table("./train/y_train.txt")
train_subject  <- read.table("./train/subject_train.txt")

# binding train and test with activity as Factor
tot_activity     <- rbind(test_activity, train_activity)
tot_activity[,1] <- as.factor(tot_activity[,1])
tot_subject      <- rbind(test_subject, train_subject)

# naming the new column names from V1 and V2 into "activity" and "subject"
my_df <- cbind(my_df, tot_activity,tot_subject)
colnames(my_df)[length(names(my_df))-1] <-"activity"
colnames(my_df)[length(names(my_df))]   <-"subject"

## QUESTION 3 ##
# Making the activity in descriptive labels from the activity-labels.txt 
labels <- read.table("activity_labels.txt")
labels <- labels[,2]
levels(my_df$activity) <- labels 


## QUESTION 4 ##
# Appropriately labels the data set with descriptive variable names from the features.txt 
# activity and subject already labeled
# this was a lot of work : I wonder if this was meant in the assignment ?
# I had little clue as to what the variables really meant
temp <- names(my_df)
temp <- tolower(temp)
temp <- gsub("^t", "time", temp)
temp <- gsub("^f", "frequency", temp)
temp <- gsub("acc", "acceleration", temp)
temp <- gsub("gyro", "gyroscope", temp)
temp <- gsub("mag", "magnitude", temp)
temp <- gsub("\\(\\)", "", temp)
temp <- gsub("\\(tbody", "timebody", temp)
temp <- gsub("\\(", "", temp)
temp <- gsub("\\(", "", temp)
names(my_df) <- temp


# creating the table format for use in dplyr
my_tb <- tbl_df(my_df)

## QUESTION 5 ##

# using the summarise_each function from dplyr and using "View" for a seperate window
my_tidy_data <- my_tb %>% arrange(activity, subject) %>% group_by(activity, subject) %>% summarise_each(funs(mean))
View(my_tidy_data)

# writing the file as .txt file to my_tidy_data.txt
write.table(my_tidy_data, file="my_tidy_data.txt", row.names = FALSE)

# get back to the origional directory from where we started
setwd(startwd)


```


