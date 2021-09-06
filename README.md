![](./PNG_files/image_1.png)

# An attempt to predict the future: coding machine learning and AI models to predict pharmaceutical company stocks.

The main objective of this project is to code machine learning and AI models in an attempt to predict future closing prices for stocks. Under the understanding that this is a challenging and subjective task, our main goal is to get as close as possible to a good model to use in real life investing. 

Additionally, in light of current world's relevant events, we selected the main pharmaceutical companies which are leading the market in developping COVID vaccines. Pfizer, Moderna, Johnson & Johnson and Astrazeneca; each of these companies have a different history and period for when they went public in the market, this was also an important point of consideration for this project.

All of the DATA analyzed was fetched from Yahoo Finance, and all of the different models ran for this project used the same source of information/data set-up.

```python:
start = dt.datetime(2010,1,1)
end = dt.datetime.now()
tickers = ['PFE', 'MRNA', 'JNJ', 'AZN']

filenames = []

for ticker in tickers:
    if ticker == 'MRNA':
        df = yf.download(ticker, dt.datetime(2018,12,7), end)
    else:
        df = yf.download(ticker, start, end)
    filename = f'{ticker}_stock_prices.csv'
    filenames.append(filename)
    df.to_csv(filename)
    
for filename in filenames:
    if filename.startswith('AZN'):
        azn_df = pd.read_csv('AZN_stock_prices.csv', index_col='Date', parse_dates=True)
    elif filename.startswith('MRNA'):
        mrna_df = pd.read_csv('MRNA_stock_prices.csv', index_col='Date', parse_dates=True)
    elif filename.startswith('JNJ'):
        jnj_df = pd.read_csv('JNJ_stock_prices.csv', index_col='Date', parse_dates=True)
    else:
        pfe_df = pd.read_csv('PFE_stock_prices.csv', index_col='Date', parse_dates=True)
```
-----------------

## Models studied and coded:

### ARMA - Machine Learning - Time Series Analysis






