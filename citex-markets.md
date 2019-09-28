# Interface of CITEX markets

## 1. Version
Version | Time |   Remark
-- | -- |   --
0.1 | 2019-01-26

## 2. Description
The interface is used to obtain the markets information from CITEX. e.g. eth/usdt, eth/btc etc

## 3. URL

``` 
Url:            https://api.citex.co.kr/v1/markets/common/ticker
Method:         GET

```
### Headers

``` 

```
### Request:

 Param                  |     Type        |Mandatory|          Description         
------------ |     -------------|--|         -----------
nil|nil|nil|nil


## 4. Response：
### Parameters
 Param                      |     Type        |        Description   
 ------------ |-------------|-----------
 lastPrice|string|The latest price
 volume|string|Volume
 high|string|24h Highest price
 low|string|24h Lowest price
 amount|string|Amount
 ratio|string|Rate of up/down
 tradeUrl|string|Trade url
 baseAssetLogo|string|Base currency logo
 baseAsset|string|Base currency
 baseAssetName|string|Base currency name
 quoteAsset|string|Quote currency
 quoteAssetName|string|Quote currency name


### Headers

``` 
Content-Type:   Application/Json
```

### Successful：
HTTP/1.1 200 OK
```
[
    {
        "volume": "0",
        "quoteAssetName": "USDT",
        "high": "0",
        "amount": "0",
        "low": "0",
        "baseAssetLogo": "https://citex-public.oss-cn-hongkong.aliyuncs.com/images/token-logo/eth.png",
        "baseAssetName": "ETH",
        "baseAsset": "eth",
        "tradeUrl": "https://www.citex.co.kr/#/trade/3/16",
        "quoteAsset": "usdt",
        "lastPrice": "0",
        "ratio": "0.0000"
    },
    {
        "volume": "0",
        "quoteAssetName": "USDT",
        "high": "0",
        "amount": "0",
        "low": "0",
        "baseAssetLogo": "https://citex-public.oss-cn-hongkong.aliyuncs.com/images/token-logo/btc.png",
        "baseAssetName": "BTC",
        "baseAsset": "btc",
        "tradeUrl": "https://www.citex.co.kr/#/trade/3/21",
        "quoteAsset": "usdt",
        "lastPrice": "0",
        "ratio": "0.0000"
    },
    {
        "volume": "11700",
        "quoteAssetName": "ETH",
        "high": "0.00006477",
        "amount": "0.757809",
        "low": "0.00006477",
        "baseAssetLogo": "https://citex-public.oss-cn-hongkong.aliyuncs.com/images/token-logo/ctt.png",
        "baseAssetName": "CTT",
        "baseAsset": "ctt",
        "tradeUrl": "https://www.citex.co.kr/#/trade/1/25",
        "quoteAsset": "eth",
        "lastPrice": "0.00006477",
        "ratio": "0.0000"
    }
]
```