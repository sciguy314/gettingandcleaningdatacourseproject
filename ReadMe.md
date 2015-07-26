##ReadMe.md

The run_analysis.R program performs the following transformations on the original UCI HAR dataset.

The **features.txt** file was read and the result was a data frame (**features**) of column names. This was edited to standarize appearance by removing pairs of parentheses and converting dashes to dots.

The **activity_labels.txt** file was read into the data frame **activities**.

The testing and training data were acquired in separate operations. First, subject and activity information for the type of activity was read into separate data frames (**test_subjects** and **test_activity**). Then the data was read. The three data frames one were then combined using cbind. At this time a new column, **type**, was also introduced to distinguish between "test" and "train" sets when all the data was eventually combined. Column names were added using the **features** data frame as the column names. This resulted in the data frame **test_complete**.The process was repeated for the training data.

rbind was then used to combine the test and training data into one dataset, **completeData**.

The **activities** data frame was then used to convert the column **activity** in **completeData** from an integer to a factor, providing text descriptions of each type of activity.

A select command was then used to extract columns of interest, which were **subject**, **activity** and any column containing either "mean" or "std", and stored in **subsetData**.

**subsetData** was then grouped by **subject** and **activity** and the summarize_each command was used to compute the mean of all the columns containing mean or standard deviation data. The result was stored in the data frame **tidyData**.

This column names that had been computed were then prefixed with "avg." to indicate that the information represented the mean of the original data.

**tidyData** was then written to a file using write.table .

**tidyData** can be read using the following statement:
'''{R}
tidyData <- read.table(filename, header = TRUE)  
'''