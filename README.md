DataCleaningPeerAssignment

Explanation of run_analysis.R Script
====================================

Preliminaries:

  Relevant data to be included in dataset was loaded.  The date and time of the download (Sun Apr 20 19:31:20 2014) was   noted. 

  "Inertial signal" data was ignored since the raw, unprocessed data was not needed for the assignment.
  No libraries used outside of base package.  {markdown} and {knitr} were used for the R Markdown script.  

Exploratory Analysis:

  The dimensions and heads of the data sets were examined.  A check for missing values (done in Tidy Data Set Constructi   on below) showed that there were none.
  
Initial Tidy Data Set Construction:

  1. Combine training and test data sets.
	    a) adding the subject vectors to the training and test data set data frames
	    b) equating the names of the subject vectors
	    c) combining the training and test data frames
	    d) use the feature vector to name the variables
	    e) append the "activity" and "subject" vectors to the  data frame (last two columns)
	    f) change variable names to lower case
  2. Apply descriptive activity names for the activities in the data set.
  3. The structure of the data set was explored further using the str() and is.na() functions.
  
Meaningful Variable Extraction:

  The assignment called for the extraction of variables limited to the means and standard deviations of each 
  measurement. The greps() function with the argument "Fixed=TRUE" was used to yield a vector of length 66.  (The         assignment instructions were ambiguous but were interpreted as to include only variables labeled "mean()" and "std()".   The variables "meanFreq()", "gravityMean", "tBodyAccMean", "tBodyAccJerkMean", "tBodyGyroMean", and 
  "tBodyGyroJerkMean" were excluded.) The data set was subsetted according to this vector and combined with the activity   and subject vectors.
  
Creation of Second Tidy Data Set:

  The aggregate() function was used to create a second, independent tidy data set with the average of each variable for   each activity (rows 1-6) and for each subject (rows 7-36).  The "activity" and "subject" columns were prepended and a   local file was created using the write.table() function.  A pdf of the spreadsheet was uploaded to the grading site.
