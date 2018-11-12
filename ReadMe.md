# Trends in Maharashtra Mandi Prices
For this Project the data was provided by Social Cops for around two years for 33 Districts, 349 APMC ( Mandi's) and 201 Commodities. This objective was to understand trends in various APMC-Mandi and come up with usefull insights.

## Warming Up
Following libraries have been used in this Project
1. Numpy
2. Pandas
3. Matplotlib
4. Seaborn
5. Seasonal
6. Datetime


## Process

### 1. Pre-Processing

The data was collected directly from mandis of maharashtra. We cleaned the data of typing errors, and changed the local names of commodities in order to maintain uniformity in the dataset.

### 2. Adjusting Prices For Inflation

The prices were adjusted for inflation in order to make the prices for different years comparable.

### 3. Filtering Outliers

In order to filter the outliers, we used Inter Quartile Range (IQR) method. Anything below 1.5 IQR from 1st quartile and anthing above 1.5 IQR from 3rd quartile was termed as an Outlier.

### 4. Narrowing Down Dataset

For this project we only considered APMC-MANDI for which we had at least 20 observations.

### 5. Creating Uniform Timeseries
After filtering out outliers and removing APMC-MANDI which had less than 20 observations, we created a uniform timeseries filled it with average price of that commodity across different commodities for that day.

### 6. Detect Seasonality Type
We could detect the seasonality for each combination using two methods
#### 1. Using Visual Inspection
We were limited by the amount of data for each APMC-MANDI and could not come out very confidently about the seasonality.

#### 2. Assuming both Additive and Multiplicative seasonality
We try both additive and multiplicative seasonality, and assume the one which has less auto corelation after deseaonlising.


### 7. De-Seasonalise prices for each Commodity and APMC
We could not very strongly determine the seasonality for each APMC-MANDI, so we assumed that the seasonality is additive and used Holt Winter's method to De-Seasonalise the prices.

### 8. Detect Crop Type For Each Commodity
We detect the crop type for each commodity using internet from sites like agritech, apnikheti.in.

### 9. Observations

1. Rabi Crops show more variation in prices as compared to Kharif Crops
2. Declaring a MSP results in less variation of prices
3. Larger Mandis show greater variation in Prices

