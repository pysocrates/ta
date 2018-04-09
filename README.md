# Technical Analysis Library in Python

It is a technical analysis library to financial time series datasets. You can use to do feature engineering. It is builded on pandas python library.

Features you can find out here:

#### Volume

* Accumulation/Distribution Index (ADI)
* On-Balance Volume (OBV)
* On-Balance Volume mean (OBV mean)
* Chaikin Money Flow (CMF)
* Force Index (FI)
* Ease of Movement (EoM, EMV)
* Volume-price Trend (VPT)

#### Volatility

* Average True Range (ATR)
* Bollinger Bands (BB)
* Keltner Channel (KC)
* Donchian Channel (DC)

#### Trend

* Moving Average Convergence Divergence (MACD)
* Average Directional Movement Index (ADX)
* Vortex Indicator (VI)
* Trix (TRIX)
* Mass Index (MI)
* Commodity Channel Index (CCI)
* Detrended Price Oscillator (DPO)
* KST Oscillator (KST)
* Ichimoku Kinkō Hyō (Ichimoku)

#### Momentum

* Money Flow Index (MFI)
* Relative Strength Index (RSI)
* True strength index (TSI)

#### Others

* Daily Return (DR)
* Cumulative Return (CR)


# How to use


```sh
> virtualenv -p python3 virtualenvironment
> source virtualenvironment/bin/activate
> pip3 install ta
```

To use this library you should have a financial time series dataset including “Timestamp”, “Open”, “High”, “Low”, “Close” y “Volume” columns.

You should clean or fill nan values in your dataset before add technical analysis features.

You can get code examples in "examples_to_use" folder.

If you don't know any feature you can view the notebook: "examples/visualize_features.ipynb".

Note: To execute the notebook you will need install 'matplotlib' and 'jupyter lab'. So:

```sh
> pip3 install matplotlib==2.1.2
> pip3 install jupyterlab==0.31.12
```


#### Example adding all features

```python
import pandas as pd
from ta import *

# Load datas
df = pd.read_csv('your-file.csv', sep=',')

# Clean nan values
df = utils.dropna(df)

# Add ta features filling Nans values
df = add_all_ta_features(df, "Open", "High", "Low", "Close", "Volume_BTC",
                            fillna=True)
```


#### Example adding individual features

```python
import pandas as pd
from ta import *

# Load datas
df = pd.read_csv('your-file.csv', sep=',')

# Clean nan values
df = utils.dropna(df)

# Add bollinger band high indicator filling Nans values
df['bb_high_indicator'] = bollinger_hband_indicator(df["Close"], n=20, ndev=2,
                                                        fillna=True)

# Add bollinger band low indicator filling Nans values
df['bb_low_indicator'] = bollinger_lband_indicator(df["Close"], n=20, ndev=2,
                                                        fillna=True)
```


# Deploy to developers

```sh
> pip3 install -r requirements.txt
```


# Based on:

* https://en.wikipedia.org/wiki/Technical_analysis
* https://pandas.pydata.org/
* https://github.com/FreddieWitherden/ta
* https://github.com/femtotrader/pandas_talib


# TODO:

* generate online documentation (https://readthedocs.org/)
* add ta features
* more documentation


# Credits:

Developed by Bukosabino at Lecrin Technologies - http://lecrintech.com

We are glad to receive any contribution, idea or feedback.
