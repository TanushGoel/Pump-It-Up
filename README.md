# Pump-It-Up
Predicting which pumps are functional, which need some repairs, and which don't work at all using data from Taarifa and the Tanzanian Ministry of Water. A smart understanding of which waterpoints will fail can improve maintenance operations and ensure that clean, potable water is available to communities across Tanzania. 

The data was mapped to numerical values in the notebooks:

functional: 1

functional needs repair: 0

nonfunctional: -1

## Notes

The dataset was mainly strings for most of the features in both the training and testing datasets. The notebook "Pump_It_Up_Water_Tokenizing" was made to turn all the values of both datasets (which were put together in "PumpItUpAll.csv") into distinct integer values for each string. The missing values were then filled using MICE via Microsoft's Machine Learning Studio and separated back into the two training and testing sets ("PumpItUpTokenizedCleanedMICE_train.csv" & "PumpItUpTokenizedCleanedMICE_test.csv"). Probabalistic PCA was tried to fill in missing data, but achieved a lower accuracy. 

An ensemble of the catboost trees, random forest, and extra trees classifiers were used in the final submission. I used 30 different catboost trees simply so I could see the differences between them such as feature importances. If storage is an issue, only use one classifier and append its predictions to the submission over each fold. 


Many techniques were used in the data engineering of this project

A "geohash" feature was created using latitude and longitude features
Three geohashes were made using different precisions. The first geohash feature (geohash1) separates the area into 6 different regions and the second (geohash2) into 56 regions. The third geohash feature (geohash3) seprates the area into 946 regions in the training set, but only 857 of these are seen in the testing set.

The locations of the pumps were also displayed on an interactive heat-map of Africa specifically zoomed in on Tanzania, using the lattitude and longitude features. 
![Heatmaps](https://github.com/TanushGoel/Pump-It-Up/issues/1)

PCA (principal component analysis) was used to reduce the dimensionality of the 39-feature dataset. The dataset had very similar feature pairs such as "waterpoint_type" and "water_point_type_group" or "source" "source_type" and "source_class" which were simplified into "waterpoint" and "ss".

New features were created using existing ones. 

## Data

The data was taken from [DrivenData](https://www.drivendata.org) from the [Pump it Up: Data Mining the Water Table](https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/) competition.

### Downloads

[Submission Format](https://s3.amazonaws.com/drivendata/data/7/public/SubmissionFormat.csv)

[Test set values](https://s3.amazonaws.com/drivendata/data/7/public/702ddfc5-68cd-4d1d-a0de-f5f566f76d91.csv)

[Training set labels](https://s3.amazonaws.com/drivendata/data/7/public/0bf8bc6e-30d0-4c50-956a-603fc693d966.csv)

[Training set values](https://s3.amazonaws.com/drivendata/data/7/public/4910797b-ee55-40a7-8668-10efd5c1b960.csv)

### Features
1) amount_tsh - Total static head (amount water available to waterpoint)
2) date_recorded - The date the row was entered
3) funder - Who funded the well
4) gps_height - Altitude of the well
5) installer - Organization that installed the well
6) longitude - GPS coordinate
7) latitude - GPS coordinate
8) wpt_name - Name of the waterpoint if there is one
9) num_private -
10) basin - Geographic water basin
11) subvillage - Geographic location
12) region - Geographic location
13) region_code - Geographic location (coded)
14) district_code - Geographic location (coded)
15) lga - Geographic location
16) ward - Geographic location
17) population - Population around the well
18) public_meeting - True/False
19) recorded_by - Group entering this row of data
20) scheme_management - Who operates the waterpoint
21) scheme_name - Who operates the waterpoint
22) permit - If the waterpoint is permitted
23) construction_year - Year the waterpoint was constructed
24) extraction_type - The kind of extraction the waterpoint uses
25) extraction_type_group - The kind of extraction the waterpoint uses
26) extraction_type_class - The kind of extraction the waterpoint uses
27) management - How the waterpoint is managed
28) management_group - How the waterpoint is managed
29) payment - What the water costs
30) payment_type - What the water costs
31) water_quality - The quality of the water
32) quality_group - The quality of the water
33) quantity - The quantity of water
34) quantity_group - The quantity of water
35) source - The source of the water
36) source_type - The source of the water
37) source_class - The source of the water
38) waterpoint_type - The kind of waterpoint
39) waterpoint_type_group - The kind of waterpoint

### Libraries
- [Pandas](https://github.com/pandas-dev/pandas)
- [Numpy](https://github.com/numpy/numpy)
- [Matplotlib](https://github.com/matplotlib/matplotlib)
- [Seaborn](https://github.com/mwaskom/seaborn)
- [Scikit-Learn](https://github.com/scikit-learn/scikit-learn)
- [Catboost](https://github.com/catboost/catboost)
- [Folium](https://github.com/python-visualization/folium/tree/master/folium)
