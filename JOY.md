# JOY

### Description

The JOY module is a 2D representation of 3D data.

It shows strikes on the x-axis, expirations on the left-side y-axis, and a chosen value on the right-hand y-axis.

On the bottom there is an aggregate of all expirations.

Calls are green puts are blue.

### How to Use

The minimal format of the JOY module command is the following:

```
JOY SYMBOL PARAMETER
```

Where `SYMBOL` can be any symbol, for example `AAPL` - and parameter can be any of the parameters on the bottom of this page - for example `OI` which stands for Open Interest.

So an example of the minimal valid command would be:

```
JOY AAPL OI
```

The order of those initial 3 words does matter. However - after those obligatory three terms for the command you can any of the following optional parameters in any order:

  - `EXP=1-3,6` - to only select expirtions 1,2,3,6. Alternatively you could write `EXP=1,2,3,6`
  - `Y=0.5` - to change the size of the y-axis and reduce or increment the overlap between expirations.
  - `AGG` - this will aggregate all expirations into a single one.
  - `BARS` - will show bars for strikes instead of the default curves.
  - `BOTH` - will show both bars and curves.
  - `SUMS` - will show sums of calls and puts for each expiration and total in the form of large horizontal bars. The axis for these is on the top.
  - `SUMSONLY` - will only show the sum bars and not the strike bars
  - `MT=100` - will change the space in the margin on the top. Useful in case expirations are too close together.
  - `FLIP` - will flip the sign of put values. Useful in commands such as `JOY AAPL GXOI AGG BARS FLIP`.



### Examples

To see the aggregate gamma by open interest for the first three expirations with the Put values as negative.
```
JOY AAPL GXOI AGG BARS FLIP EXP=1,2,3
```

To see only the aggregates of Open Interest for each expiration.
```
JOY AAPL OI SUMSONLY
```

To show volume but make axis smaller and the size of the margin top smaller to create more space and less overlap.
```
JOY AAPL VOLM Y=0.2 MT=50
```


### Parameters

The following are the available parameters. Most self-explanatory, else they have description:

 - `OI` - Open Interest
 - `OPENINTEREST`    
 - `VOLM` - Volume
 - `VOLUME`    
 - `GAMMA`    
 - `VEGA`    
 - `VOL` - Volatility
 - `VOLATILITY`    
 - `DELTA`    
 - `THETA`    
 - `RHO`    
 - `THEO` - Theoretical Price
 - `BID`    
 - `BIDSIZE`    
 - `ASK`    
 - `ASKSIZE`    
 - `PRICE`    
 - `CHANGE`    
 - `SIZE` - size of last trade
 - `TURN` - turnover
 - `CHANGEPCT` - change percent
 - `OPEN`
 - `HIGH`    
 - `LOW`    
 - `CLOSE`    
 - `PREVCLOSE` - previous day's close price
 - `PREVVOLM` - previous day's volume
 - `GXOI` - gamma multiplied by Open Interest (naive gamma exposure)
 - `DXOI` - delta multiplied by Open Interest
 - `TXOI` - theta multiplied by Open Interest
 - `VXOI` - vega multiplied by Open Interest
 - `OICH` - one-day change in Open Interest

The following parameters are derived from processing each options order and categorizing them as a BUY,SELL, or UNDEFINED.

 - `VALUEUND` - total value of undefined trades
 - `VOLMUND` - total volume of undefined trades
 - `COUNTUND` - total count of undefined trades
 - `VALUESELL` - total value of sell trades
 - `VOLMSELL` - total volume of sell trades
 - `COUNTSELL` - total count of sell trades
 - `VALUEBUY` - total value of buy trades
 - `VOLMBUY` - total volume of buy trades
 - `COUNTBUY` - total count of buy trades
 - `VALUEBS` - sum of buy trades minus sell trades
 - `COUNTBS` - count of buy trades minus sell trades
 - `VOLMBS` - volume of buy trades minus sell trades
 - `VALUE` - total value of all trades
