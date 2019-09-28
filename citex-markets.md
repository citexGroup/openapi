# Public Rest API for Citex

# General API Information
* The base endpoint is: "https://api.citex.co.kr/v1".
* All endpoints return either a JSON object.
* Any endpoint can return Empty list which cause request FAILED.
```javascript
[]
```
* For `GET` endpoints, parameters must be sent as a `string` or `int`.

# LIMITS
* All API request rate limit is `1 time/sec`. It will cause request failed if request more than 1 time/sec. `Suggestion:` Every time to request, make sure the response include right data.

# OUTLOOK

[Public API Endpoints](#public-api-endpoints)

    1.Fetch Exchange Infomation
    2.Fetch Tickers Data
    3.Fetch Orderbook Data
    4.Fetch Historical Trades Data
    5.Fetch Candelstick Data


# Public API Endpoints
## 1. Fetch Exchange Infomation
* `Request` 

   GET /exchangeInfo
* `Response` 
```javascript
[
    {
        'symbol': 'eth_btc', 
        'status': 'trading', 
        'baseAsset': 'eth', 
        'baseAssetPrecision': 3, 
        'quoteAsset': 'btc', 
        'quoteAssetPrecision': 6
     }
     ...
]     
```
* `status`:Contract status. (trading:can trade. stopping:cannot trade)

## 2.	Fetch Tickers Data
* `Request` 

   GET /alltickers
* `Response` 
```javascript
{
    'timestamp': 1569493791387, 
    'ticker': 
            [
                {
                    'symbol': 'eth_btc', 
                    'high': '0.020454', 
                    'vol': '69465.54', 
                    'last': '0.02018', 
                    'low': '0.01984', 
                    'buy': '0.019884', 
                    'sell': '0.020454'
                }
                ...
            ]
}
```
* `vol`: trading volume starting at 00:00 utc-8.

## 3.	Fetch Orderbook Data
* `Request` 

   GET /depth
* `Param` 

   String symbol : eth_btc
   
   Int size : Not required, default 50, max 50
   
* `Response` 
```javascript
{
    'asks': 
            [
                ['0.020893', '0.068'],
                ...
            ],
    'bids': [
                ['0.020277', '2.8'],
                ...
            ]
}
```
* `symbol`:symbol name
* `bids`:max 50 bids, order by desc
* `asks`:max 50 asks, order by asc

## 4.	Fetch Historical Trades Data
* `Request` 

   GET /api/v1/common/allticker
* `Param` 

   String symbol : eth_btc
   
   Int size : Not required, default 50, max 50
   
* `Response` 
```javascript
[
    {
        'timestamp': 1569551029905621, 
        'price': '0.020627', 
        'amount': '0.07', 
        'side': 'buy'
    },
    ...
]
```
* `Order`:The first record is the the most recent trade.

## 5.	Fetch Candelstick Data
* `Request` 

   GET /mapi/quot/queryCandlestick
* `Param` 

   String symbol : eth_btc
   
   Int type : Not required, default 1(1min). (1,3,5,15,30,60,120,240,360,1440)
   
   Int size : Not required, default 10, no limit
   
* `Response` 
```javascript
[
    [
        1569551400000, '0.020611', '0.020625', '0.020611', '0.020616', '29.804'
    ]
    ...
]
```
* Every list:timestamp, open, high, low, close, volume
* The first record in lists is the most recent data
