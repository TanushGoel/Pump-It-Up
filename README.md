# Pump-It-Up
Predicting which pumps are functional, which need some repairs, and which don't work at all using data from Taarifa and the Tanzanian Ministry of Water. A smart understanding of which waterpoints will fail can improve maintenance operations and ensure that clean, potable water is available to communities across Tanzania. 

The data was mapped to numerical values in the notebooks:
functional: 1
functional needs repair: 0
nonfunctional: -1

## Data

The data was taken from [DrivenData](drivendata.org) from the [Pump it Up: Data Mining the Water Table](https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/) competition.

**Features**
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
