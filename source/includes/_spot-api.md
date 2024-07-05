# Spot Endpoint

## Spot Wallet

```GET /spot/wallet```

Get user assets or positive assets data.

> Response

```json
{
    "data": {
        "id": 1576,
        "memberId": 79010,
        "coin": {
            "name": "Bitcoin",
            "nameCn": "Bitcoin",
            "unit": "BTC",
            "status": 0,
            "minTxFee": 0.001,
            "maxTxFee": 0.001,
            "cnyRate": 0.0,
            "usdRate": 0.0,
            "enableRpc": 1,
            "sort": 1,
            "canSend": 1,
            "canWithdraw": 1,
            "canRecharge": 1,
            "canTransfer": 0,
            "canAutoWithdraw": 1,
            "withdrawScale": 5,
            "withdrawThreshold": 0.1,
            "minWithdrawAmount": 2.0E-5,
            "maxWithdrawAmount": 10.0,
            "minRechargeAmount": 1.0E-6,
            "isPlatformCoin": 1,
            "isToken": 0,
            "hasLegal": false,
            "allBalance": null,
            "coldWalletAddress": "14QZK9h8udeB6riNfrNRYhK5ptHzJTmjM5",
            "hotAllBalance": null,
            "blockHeight": null,
            "minerFee": null,
            "infolink": "",
            "information": "BTC",
            "accountType": 0,
            "depositAddress": "mi1Q3VpBYr7XJL9pP51Vpw1WLc1eXSQxzX",
            "memoAdjust": null,
            "scanTxidWeburl": "https://www.blockchain.com/btc/tx/",
            "scanAddressWeburl": "https://www.blockchain.com/btc/address/",
            "visible": 1,
            "testMode": 0,
            "networkCoins": null,
            "icon": null,
            "defaultIcon": null,
            "spotTradable": null
        },
        "balance": 0.0,
        "frozenBalance": 0.0,
        "lockedBalance": 0.0,
        "toReleased": 0.0,
        "networkCoin": null,
        "address": "mgD26J1cL3AmC6URuBo7gbVrEYJ6trDQ9S",
        "tag": null,
        "memo": null,
        "isLock": 0
    },
    "code": 0,
    "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |

### Parameter:

| Name   | Type    | Required | Description                                               |
|--------|---------|----------|-----------------------------------------------------------|
| asset  | String  | No       | If blank, then query all positive assets that user have   |


## Spot Market

```GET /spot/market```

> Response

```json
{
  "data": [
    {
      "symbol": "BTC/USDT",
      "open": 0,
      "high": 0,
      "low": 0,
      "close": 23379.73,
      "chg": 0,
      "change": 0,
      "volume": 0.0,
      "turnover": 0,
      "lastDayClose": 23379.73,
      "usdRate": 23379.73,
      "baseUsdRate": 1,
      "zone": 0,
      "baseCoinScale": 2
    },
    {
      "symbol": "ETH/USDT",
      "open": 0,
      "high": 0,
      "low": 0,
      "close": 1777.74,
      "chg": 0,
      "change": 0,
      "volume": 0.0,
      "turnover": 0,
      "lastDayClose": 1777.74,
      "usdRate": 1777.74,
      "baseUsdRate": 1,
      "zone": 0,
      "baseCoinScale": 2
    }
    ...
  ],
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |


## Spot OrderBook

```GET /spot/market/orderbook```

> Response

```json
{
  "data": {
    "ask": {
      "direction": "SELL",
      "maxAmount": 96.54808,
      "minAmount": 4.7E-4,
      "highestPrice": 50000.0,
      "lowestPrice": 23380.0,
      "symbol": "BTC/USDT",
      "items": [
        {
          "price": 23380.0,
          "amount": 53.89597
        },
        {
          "price": 23380.06,
          "amount": 0.001
        }
        ...
      ]
    },
    "bid": {
      "direction": "BUY",
      "maxAmount": 9150.74,
      "minAmount": 2.0E-4,
      "highestPrice": 23379.73,
      "lowestPrice": 0.01,
      "symbol": "BTC/USDT",
      "items": [
        {
          "price": 23379.73,
          "amount": 7.2E-4
        },
        {
          "price": 23360.0,
          "amount": 2.0
        }
        ...
      ]
    }
  },
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |


### Parameter:

| Name   | Type    | Required | Description |
|--------|---------|----------|-------------|
| symbol | String  | Yes      |             |


## Spot Market Trades

```GET /spot/market/trade```

> Response

```json
{
  "data": [
    {
      "id": "6483023c16e8ca6c5314628f",
      "symbol": "BTC/USDT",
      "price": 23379.73,
      "amount": 4.0E-5,
      "buyTurnover": 0.9351892,
      "sellTurnover": 0.9351892,
      "direction": "SELL",
      "buyOrderId": "E168630738000719",
      "sellOrderId": "E168630738833757",
      "time": 1686307388354,
      "timeString": "2023-06-09 10:43:08"
    },
    {
      "id": "6483023b16e8ca6c53146288",
      "symbol": "BTC/USDT",
      "price": 23379.73,
      "amount": 4.0E-5,
      "buyTurnover": 0.9351892,
      "sellTurnover": 0.9351892,
      "direction": "SELL",
      "buyOrderId": "E168630737952495",
      "sellOrderId": "E168630738788938",
      "time": 1686307387913,
      "timeString": "2023-06-09 10:43:07"
    }
    ...
  ],
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |


### Parameter:

| Name   | Type   | Required | Description  |
|--------|--------|----------|--------------|
| symbol | String | Yes      |              |
| size   | int    | No       | Default : 20 |


## Spot Order History

```GET /spot/order/history```

> Response

```json
{
  "data": [
    {
      "orderId": "E168653566641932",
      "memberId": 79010,
      "symbol": "BTC/USDT",
      "coinSymbol": "BTC",
      "baseSymbol": "USDT",
      "status": "COMPLETED",
      "direction": "BUY",
      "type": "MARKET_PRICE",
      "price": 0.0,
      "amountSymbol": "USDT",
      "amountType": "BASE",
      "amount": 10.0,
      "tradedAmount": 4.2E-4,
      "turnover": 10.0,
      "time": 1686535666419,
      "completedTime": 1686535666456,
      "canceledTime": null,
      "useDiscount": "0",
      "orderResource": "CUSTOMER",
      "detail": null,
      "completed": true
    },
    {
      "orderId": "E168653566392012",
      "memberId": 79010,
      "symbol": "BTC/USDT",
      "coinSymbol": "BTC",
      "baseSymbol": "USDT",
      "status": "COMPLETED",
      "direction": "BUY",
      "type": "MARKET_PRICE",
      "price": 0.0,
      "amountSymbol": "USDT",
      "amountType": "BASE",
      "amount": 10.0,
      "tradedAmount": 4.2E-4,
      "turnover": 10.0,
      "time": 1686535663920,
      "completedTime": 1686535663951,
      "canceledTime": null,
      "useDiscount": "0",
      "orderResource": "CUSTOMER",
      "detail": null,
      "completed": true
    }
    ...
  ],
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |


### Parameter:

| Name       | Type   | Required                                                       | Description                                          |
|------------|--------|----------------------------------------------------------------|------------------------------------------------------|
| symbol     | String | Yes                                                            |                                                      |
| startTime  | int    | No                                                             |                                                      |
| endTime    | int    | No                                                             |                                                      |
| status     |        | Yes                                                            | TRADING(미체결),<br> COMPLETED(체결완료),<br> CANCELED (취소) |
| size       |        | No (If startTime and endTime <br> is not set, it is mandatory) |                                                      |


## Spot Trade History

```GET /spot/trade/history```

> Response

```json
{
  "data": [
    {
      "tradeId": "72405394",
      "tradeTime": 1686535666448,
      "memberId": 79010,
      "symbol": "BTC/USDT",
      "coinSymbol": "BTC",
      "baseSymbol": "USDT",
      "direction": "BUY",
      "type": "MARKET_PRICE",
      "role": "TAKER",
      "price": 23380.0,
      "tradedAmount": 4.2E-4,
      "turnover": 10.0,
      "orderId": "E168653566641932",
      "feeSymbol": "BTC",
      "fee": 0.0
    },
    {
      "tradeId": "72405392",
      "tradeTime": 1686535663942,
      "memberId": 79010,
      "symbol": "BTC/USDT",
      "coinSymbol": "BTC",
      "baseSymbol": "USDT",
      "direction": "BUY",
      "type": "MARKET_PRICE",
      "role": "TAKER",
      "price": 23380.0,
      "tradedAmount": 4.2E-4,
      "turnover": 10.0,
      "orderId": "E168653566392012",
      "feeSymbol": "BTC",
      "fee": 0.0
    }
    ...
  ],
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |


### Parameter:

| Name       | Type   | Required                                                       | Description   |
|------------|--------|----------------------------------------------------------------|---------------|
| symbol     | String | Yes                                                            |               |
| startTime  | int    | No                                                             |               |
| endTime    | int    | No                                                             |               |
| direction  |        | Yes                                                            | BUY,<br> SELL |
| size       |        | No (If startTime and endTime <br> is not set, it is mandatory) |               |


## Spot Order

```POST /spot/order```

> Response

```json
{
  "data": "E168629530081880",
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |


### Parameter:

| Name      | Type   | Required | Description                   |
|-----------|--------|----------|-------------------------------|
| symbol    | String | Yes      |                               |
| price     | string | Yes      |                               |
| amount    | string | Yes      |                               |
| direction | string | Yes      | BUY,<br> SELL                 |
| type      | string | Yes      | LIMIT_PRICE,<br> MARKET_PRICE |


## Spot Order Cancel

```POST /spot/order/cancel/{orderId}```

> Response

```json
{
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |


### PathValue:

| Name    | Type   | Required | Description  |
|---------|--------|----------|--------------|
| orderId | String | Yes      |              |


## Spot Order Cancel ALL

```POST /spot/order/cancel/all```

> Response

```json
{
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |


### Parameter:

| Name    | Type     | Required | Description  |
|---------|----------|----------|--------------|
| symbol  | String   | Yes      |              |


## Spot Current K-Line

Get current chart data

```GET /spot/market/kline/current```

> Response

```json
{
  "data": {
    "openPrice": 23379.73,
    "highestPrice": 23379.73,
    "lowestPrice": 23379.73,
    "closePrice": 23379.73,
    "time": 0,
    "endTime": 0,
    "timeString": "1970-01-01 00:00:00",
    "endTimeString": null,
    "period": "1min",
    "count": 0,
    "volume": 0,
    "turnover": 0
  },
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |


### Parameter:

| Name        | Type    | Required  | Description                                                                                               |
|-------------|---------|-----------|-----------------------------------------------------------------------------------------------------------|
| symbol      | String  | Yes       |                                                                                                           |
| resolution  | String  | Yes       | 1 (1 minute)<br/> 30 (30 minute)<br/> 60 (1 hour)<br/> 1D (1 day)<br/> 1W (1 week)<br/> 1M (1 month)<br/> |


## Spot K-Line History

```GET /spot/market/kline/history```

Get chart history data

> Response

```json
{
  "data": [
    [
      1686283500000, // time
      23379.73, // open price
      23379.73, // high price
      23379.73, // low price
      23379.73, // close price
      0, // total qty
      "2023-06-11 23:03:00",
      "2023-06-11 23:05:00"
    ],
    [
      1686283500000,
      23379.73,
      23379.73,
      23379.73,
      23379.73,
      0, 
      "2023-06-11 23:05:00",
      "2023-06-11 23:06:00"
    ]
    ...
  ],
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name           | Type   | Required | Description              |
|----------------|--------|----------|--------------------------|
| Authorization  | String | Yes      | Auth Key (type = Bearer) |
| x-api-key    | String | Yes      | API key                  |


### Parameter:

| Name       | Type    | Required | Description                                                                                               |
|------------|---------|----------|-----------------------------------------------------------------------------------------------------------|
| symbol     | String  | Yes      |                                                                                                           |
| from       | String  | Yes      | ex) 1686516139000                                                                                         |
| to         | String  | Yes      | ex) 1686535279316                                                                                         |
| resolution | String  | Yes      | 1 (1 minute)<br/> 30 (30 minute)<br/> 60 (1 hour)<br/> 1D (1 day)<br/> 1W (1 week)<br/> 1M (1 month)<br/> |
