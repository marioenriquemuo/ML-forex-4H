# ML-forex-EURUSD4H
Machine learning model for Forex prediction using 4H candles and the historical data from Forex

**As a friendly reminder, this was an academic project and has never been used in a real-life. It should not be used as financial advice that being said please feel free to play with it.**

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

