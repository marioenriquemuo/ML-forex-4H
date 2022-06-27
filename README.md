# ML-forex-EURUSD4H
Machine learning model for Forex prediction using 4H candles and the historical data from Forex

**As a friendly reminder, this was an academic project and has never been used in a real-life. It should not be used as financial advice, that being said please feel free to play with it.**

## Initial data set.

* Observations: 
  * 12,787 for validation
  * 100,557 for training
* Columns: 10
* Start date: 11/5/2001
* End date: 3/3/2022

Working and analyzing data is the date after applying new columns (Metrics) and for patterns found.


## Metric and Dymencion description

* date: Date of the observation, based on the NY time.
* bull: Based on the develop function, it will identify as 1 a bull market or 0 as a bearish market
* D_MVA200: Distance from the close of the Candle to the position of the simple moving average of 200 observations.
* length: the number of candles that create the double top of bottom pattern
* height: The height of the double top of bottom pattern
* type: Type of pattern (Double top or Double bottom)
* entry: Price of entry for the possible entry.
* stop: Min or Max price for the Double patterns
* gain: Result of the patterns. 1 indicates it was a successful trade 0 means it wasn't a successful trade.
* target: Target price that shows a successful trade.
* stop_trade: Stop price including the amount stated by the Average true range (ATR) for the 14 candle observation. 
* resistance_support: If the patterns interact with previews define resistance or support area.
* MVA200_interact: If the pattern interacts with the MVA200
* D_target: Distance from the close of the candle to the target price.
* D_stop_trade: Distance from the close of the last candle to the stop price point.
* Pair: Forex pair that was observed.

*Note:* To align all pairs and maintain comparable metrics the following were divided by the ATR of 14 observations. So distance is measured by how many ATRs we have. 
* height
* D_MVA200
* D_target
* D_stop_trade


## Funciones.py File

On the functions file, you are going to find the following functions:

* newcolumns( df ): 
  * Input: Raw historical data frame with the following columns ['bidopen', 'bidclose', 'bidhigh', 'bidlow','tickqty']
  * This function will include all the necessary metrics and dimensions.

* double( df ):
  * Input: The resulting data frame from the previews function ( newcolumns(df) ). **Do not overtire the newcolumns df**
  * This function will identify double top or double bottom patterns on the historical data.

* gain_calculator( double, newcolumns  )
  * Input: Double and newcolumns data frames.
  * This function will review the following candles after the double observation and assess if the theoretical trade was successful, creating a new dimension GAIN. where 1 will be applied for successful results and 0 for failure.

* cleandataframe( DF ):
  * Input: The resulting data frame from the gain_calculator function.
  * This function will remove unnecessary columns and organize the data.


## EDA Folder

Data graphs and initial data analysis. 

## First Model testing Folder

In this folder, you are going to find the first initial test of different Machine learning models some of them are tree base and different parameters like PCA and normalizing.

### Tested models
* DecisionTreeClassifier
* RandomForestClassifier
* KNeighborsClassifier
* LogisticRegression
* SVC ( Support Vector Machine )
* GaussianNB
* BernoulliNB
* GradientBoostingClassifier
* LGBMClassifier
* XGBClassifier

### Tested data frames
* All data
* Only bull data
* Only bearish data
* Normalized data
* PCA data
* Oversample data
* Undersample data


