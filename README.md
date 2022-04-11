# Week-4-R-activity-dplyr.R

#Week 4: dplyr package

install.packages("dplyr")
library (dplyr)

#Task: Write the function to get a dataset from Base R: HairEyeColor
#and give the dataset a new name of your choice
HairEyeColor

HEC <- HairEyeColor

#See the top rows of the data
#TASK: Write the function to see the top rows of the data
head (HEC,2)

#Install and call the package dplyr
#TASK: Write the functions to install and call dplyr
install.packages("dplyr")
library (dplyr)


#Let's just see the hair and sex columns
#Task: Write the function to 'select' just the hair and sex columns 
#(hint: use the 'select' function)
HEC <- as.data.frame(HairEyeColor)
library (dplyr)
select (HEC,Hair,Sex)

#Let's name the dataset with just the two columns, Hair and Sex
#TASK: Write the function to save the two columns as a new dataset
#and give it a name
HEC1 <- select (HEC,Hair,Sex)


#Let's get rid of the Sex column in the new dataset created above
#TASK: Write the function that deselects the sex column
#(hint: use the 'select' function to not select a -column)
select (HEC1, -Sex)

#Let's rename a column name
#TASK: Write the function that renames 'sex' to 'gender'
rename (HEC1, gender = Sex)

#Let's make a new dataset with the new column name
#TASK: Write the function that names a new dataset that includes the 'gender' column
HEC2 <- rename (HEC1, gender = Sex)

#Let's 'filter' just the males from our dataset
#TASK: Write the function that includes only rows that are 'male'
filter (HEC2, gender == "Male")


#Let's 'group' our data by gender
#TASK: Write the function to group the data by gender (hint: group_by)
group_by (HEC2, gender)

#Let's see how many students were examined in the dataset (total the frequency)
#TASK: replace 'datasetname' with the name of your dataset and get the total
#After you run it, write the total here:_592__
total=mutate(datasetname, total=cumsum(Freq))

total = mutate(HEC, total=cumsum(Freq))

#Since we have a males dataset, let's make a females dataset
#TASK: Write the function that includes only rows that are 'female'
filter (HEC2, gender == "Male")

#And now let's join the males and females
#TASK: Write the function that joins the male and female rows 
#(hint: try using 'union' or 'bind_rows')

HEC3 <- filter (HEC2, gender == "Male")
HEC4 <- filter (HEC2, gender == "Female")

bind_rows (HEC3,HEC4)

#Optional Task: add any of the other functions 
#you learned about from the dplyr package

#Retain only unique/distinct rows from dataset.
distinct (HEC)

#Group input by rows
rowwise = (HEC)
