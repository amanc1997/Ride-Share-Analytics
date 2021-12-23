# Ride Share Analytics and Prediction

## Introduction
Bike sharing has been prevalent for decades in various parts of the world. Bike share programs, on the other hand, have grown in popularity and prevalence in the recent decade, both in the United States and globally. 
The introduction of third-generation bike share systems, which use smart cards and key fobs to electronically lock and unlock bicycles from docking stations, has aided this growth. 
The effectiveness and applicability of the initiatives, which were first adopted in larger cities, has prompted smaller localities to begin their own. 
Access to a low-cost public transportation option, enhanced health through greater physical activity, improved connected-ness, flexible mobility, emission reduction, lower fuel use, support for multi-modal connections, and reduced congestion on roadways are all advantages of bike share programs. 
While the usefulness, application, and impact of bike sharing in nations that have had it for a long time have been widely investigated, these programs are just beginning to expand in the United States and have received less investigation. As a result, in recent years, US cities have focused on building additional bike infrastructure to improve bike activity and safety, including bike sharing programs, bike lanes, individual bike lanes, and green passes.


## Data

The information we are going be looking into is downloaded and extricated from Kaggle\cite{dataset}. This US bicycle share information of Bikeshare contains passages tested from the cities of Chicago, New York and Washington for the year 2017. The dataset consists of attributes like Start Time, End Time, Duration, Start Station, End Station, Gender, User Type and Birth Year for the cities of Chicago and New York. However for the city of Washington attributes - Gender and Birth Year are missing.The dataset consists of 9 attributes.The attributes are:
```
    *.'#': containing the unique ID of  the bike share.
    *.'Start Time': containing the start time in timestamp format.
    *.'End Time': containing the end time in timestamp format.
    *.'Trip Duration': containing the duration of the trip in seconds.
    *.'Start Station': containing the name of the starting point of the bike share.
    *.'End Station': containing the name of the end point of the bike share.
    *.'User Type': containing whether the person is a subscriber or a customer.
    *.'Gender': containing the sex of the person.
    *.'Birth Year': containing the Year of birth for a particular person.
```

## Results

In the EDA phase we observed that the classes are highly imbalanced (3:1), in order to mitigate this our first approach was take all the tuples of the lesser numbered class and take a sample of the higher numbered class whose size is about (1.2) times the size of lower class. This we believed would represent the class-imbalance and help us create a better model. With this newly created dataframes for both the cities, we started by applying logistic regression and decision-tree rf-dt based algorithms on our dataset with the target variable as gender_binary (one-hot encoded values of gender) and features as trip_duration, user_type_binary, trip_day_night and trip_end_hour. We have chosen Area Under Receiver Operating Characteristic (AUROC) curve as our accuracy metric alongside the sklearn accuracy metric, since AUROC gives an accurate score despite the imbalanced nature of the class.

