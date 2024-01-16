# resalePrediction
Contains the scripts and datasets for HDB resale price prediction


## feature_engineering:

The dataset that will be transformed is *“ResaleflatpricesbasedonregistrationdatefromJan2017onwards.csv”*

From there, using the street name, the Google Maps API is called to get the coordinates of the street, and combined into a single column. This gives the *“street_coord.csv”* file.

Continuing from there, using data from *"mrt_lrt_data.csv"*, for each street, the coordinates of each train station were used to calculate the Euclidean distance, and the shortest one was chosen. This might not be the most computationally efficient method and is an area to improve on.

With the 2 coordinates of start and destination (street and train station respectively), the OneMap API is called and the route data is returned in the response. Travel and walk time was taken from the response and added on as columns to produce the final dataset *"complete_street_data.csv"*, which will be used as supplementary data in the main script.


## resale_prediction:

Data is further tweaked to be usable, and new columns with the label-encoded values of the original columns are added. The travel and walk times are mapped to the street names and the final dataset is used for training.


## Find out more
I've written about the process and considerations here: https://medium.com/@zachang97/juicing-your-data-for-boosts-in-accuracy-64349df485ac
Feel free to have a read :)
