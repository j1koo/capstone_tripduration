# capstone_tripduration
Capstone Project Title: Investigating factors influencing taxi trip duration and a comparative analysis of prediction models)

#load train and test sets
train <- read.csv("/Users/joellekoo/Downloads/all/train.csv", stringsAsFactors = FALSE, header = TRUE)
test <- read.csv("/Users/joellekoo/Downloads/all/test.csv", stringsAsFactors = FALSE, header = TRUE)

#Summary of train and test sets
summary(train)
summary(test)

#Structure of train and test sets
str(train)
str(test)

#Check for missing values
sapply(train, function(x) sum(is.na(x)))
sapply(test, function(x) sum(is.na(x)))
#Two attributes missing from test set: dropoff_datetime and trip_duration
#Merge/Combine test and train sets provided to maintain consistency and avoid any bias. We will split the merged dataset later on into test and train sets.

#Create columns for test set: dropoff_time and trip_duration
merged_set <- rbind(train, test)
rm(train)
rm(test)

str(merged_set)
summary(merged_set)
