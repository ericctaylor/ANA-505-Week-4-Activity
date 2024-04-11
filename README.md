# ANA-505-Week-4-Activity

#Week 4: dplyr package

titanicDF <- as.data.frame(Titanic)

head(titanicDF)

install.packages("dplyr")
library(dplyr)

selected_data <- select(titanicDF, Survived, Sex)

newdatasetss <- selected_data

newdataset_no_sex <- select(newdatasetss, -Sex)

newdatasetss <- rename(newdatasetss, Gender = Sex)

gender_data <- newdatasetss

male_data <- filter(gender_data, Gender == "male")

arranged_data <- arrange(gender_data, Gender)

total_frequency <- sum(titanicDF$Freq)
#TASK: After you run it, write the total here:2201

female_data <- filter(gender_data, Gender == "female")

combined_gender_data <- bind_rows(male_data, female_data)
