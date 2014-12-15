---
title: "CodeBook for Tidy UCI HAR Dataset"
author: "Elisa Di Gloria"
date: "December 15th, 2014"
output: html_document
---

# Introduction

The aim of this Code Book is to describe the output of the run_analysis.R script that you can find in this repo. 

# The script
The output of the script is a txt file "tidy_data.txt" that is a tidy version of the  University of California Irvine's (UCI's) dataset for Human Activity Recognition (HAR) using smartphones that can be used for further research and analysis. The original UCI HAR Dataset is a public domain dataset built from the recordings of subjects performing activities of daily living (ADL) while carrying a waist-mounted smartphone with embedded inertial sensor (see [UCI HAR Dataset](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)).

The script generates a combined subset of the original data by extracting the mean and standard deviation features for each of the 33 processed signals, for a total of 66 features (out of the 561 available features from the original feature vector). This combined subset contains 10299 observations of 68 variables, with activity and subject appended to the 66 features.

The combined subset is further reduced by calculating the mean of the observations by activity and subject pair to generate 180 observations (6 activities \* 30 subjects) of the same 68 variables. This dataset is tidied to generate a narrow and lean dataset containing 11880 observations with 4 variables each and is saved as a text file in the current working directory with the name *tidy_data.txt*

# Variables
In the tidyng process, the variable names have been transformed as follows:

- filtered_feature_names <- gsub("\\(\\)", "", filtered_feature_names)
- filtered_feature_names <- gsub("Acc", "-acceleration", filtered_feature_names)
- filtered_feature_names <- gsub("Mag", "-Magnitude", filtered_feature_names)
- filtered_feature_names <- gsub("^t(.*)$", "\\1-time", filtered_feature_names)
- filtered_feature_names <- gsub("^f(.*)$", "\\1-frequency", filtered_feature_names)
- filtered_feature_names <- gsub("(Jerk|Gyro)", "-\\1", filtered_feature_names)
- filtered_feature_names <- gsub("BodyBody", "Body", filtered_feature_names)


### Variable description

The Tidy dataset consists of 11880 observations summarized by activity (6 categories) and subject (30 volunteers) pairs. For each observation (row) in the Tidy dataset are provided 4 columns:

  -  subject: numeric identifier, from 1 to 30, of the subject who carried out the experiment.
  -  activity: activity name with the following possible values
    + laying
    + sitting
    + standing
    + walking
    + walking_downstairs
    + walking_upstairs
  
  -  measurement: name of the measurement for which the mean is calculated. This variable can contain one of the following 66 variables.^[Please refer the codebook with the original dataset for the explanation of these different variables.]
  
    + body-acceleration-jerk-magnitude-mean-frequency
    + body-acceleration-jerk-magnitude-mean-time
    + body-acceleration-jerk-magnitude-std-frequency
    + body-acceleration-jerk-magnitude-std-time
    + body-acceleration-jerk-mean-x-frequency
    + body-acceleration-jerk-mean-x-time
    + body-acceleration-jerk-mean-y-frequency
    + body-acceleration-jerk-mean-y-time
    + body-acceleration-jerk-mean-z-frequency
    + body-acceleration-jerk-mean-z-time
    + body-acceleration-jerk-std-x-frequency
    + body-acceleration-jerk-std-x-time
    + body-acceleration-jerk-std-y-frequency
    + body-acceleration-jerk-std-y-time
    + body-acceleration-jerk-std-z-frequency
    + body-acceleration-jerk-std-z-time
    + body-acceleration-magnitude-mean-frequency
    + body-acceleration-magnitude-mean-time
    + body-acceleration-magnitude-std-frequency
    + body-acceleration-magnitude-std-time
    + body-acceleration-mean-x-frequency
    + body-acceleration-mean-x-time
    + body-acceleration-mean-y-frequency
    + body-acceleration-mean-y-time
    + body-acceleration-mean-z-frequency
    + body-acceleration-mean-z-time
    + body-acceleration-std-x-frequency
    + body-acceleration-std-x-time
    + body-acceleration-std-y-frequency
    + body-acceleration-std-y-time
    + body-acceleration-std-z-frequency
    + body-acceleration-std-z-time
    + body-gyro-jerk-magnitude-mean-frequency
    + body-gyro-jerk-magnitude-mean-time
    + body-gyro-jerk-magnitude-std-frequency
    + body-gyro-jerk-magnitude-std-time
    + body-gyro-jerk-mean-x-time
    + body-gyro-jerk-mean-y-time
    + body-gyro-jerk-mean-z-time
    + body-gyro-jerk-std-x-time
    + body-gyro-jerk-std-y-time
    + body-gyro-jerk-std-z-time
    + body-gyro-magnitude-mean-frequency
    + body-gyro-magnitude-mean-time
    + body-gyro-magnitude-std-frequency
    + body-gyro-magnitude-std-time
    + body-gyro-mean-x-frequency
    + body-gyro-mean-x-time
    + body-gyro-mean-y-frequency
    + body-gyro-mean-y-time
    + body-gyro-mean-z-frequency
    + body-gyro-mean-z-time
    + body-gyro-std-x-frequency
    + body-gyro-std-x-time
    + body-gyro-std-y-frequency
    + body-gyro-std-y-time
    + body-gyro-std-z-frequency
    + body-gyro-std-z-time
    + gravity-acceleration-magnitude-mean-time
    + gravity-acceleration-magnitude-std-time
    + gravity-acceleration-mean-x-time
    + gravity-acceleration-mean-y-time
    + gravity-acceleration-mean-z-time
    + gravity-acceleration-std-x-time
    + gravity-acceleration-std-y-time
    + gravity-acceleration-std-z-time  
  
  -  mean: the mean of the measurements.









