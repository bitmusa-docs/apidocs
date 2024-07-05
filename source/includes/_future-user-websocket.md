# Futures Websocket User Stream

- The base API endpoint is: ```https://openapi.bitmusa.com```
- A User Data Stream listenKey is valid for 60 minutes after creation.
- Doing a PUT on a listenKey will extend its validity for 60 minutes.
- Doing a DELETE on a listenKey will close the stream and invalidate the listenKey.
- Doing a POST on an account with an active listenKey will return the currently active listenKey.
- A listenKey is a stream.
- The base websocket endpoint is: ```wss://websocket.bitmusa.com:60002```
- User Data Streams are accessed at /ws/future/<listenKey>
- A connection to only valid for 24 hours; expect to be disconnected at the 24 hour mark.

### Futures Create ListenKey

```POST /future/userDataStream```

> Response

```json
{
  "data": {
    "listenKey": "cAUzPhRQYWX1a2cE528PeAgtErBE96QWP5HpwFMSEzUC"
  },
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name          | Type   | Required  | Description              |
|---------------|--------|-----------|--------------------------|
| Authorization | String | Yes       | Auth Key (type = Bearer) |
| x-api-key     | String | Yes       | API key                  |

### Futures Keep-alive ListenKey

```PUT /future/userDataStream```

> Response

```json
{
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name          | Type   | Required  | Description              |
|---------------|--------|-----------|--------------------------|
| Authorization | String | Yes       | Auth Key (type = Bearer) |
| x-api-key     | String | Yes       | API key                  |

### Futures Close ListenKey

```DELETE /future/userDataStream```

> Response

```json
{
  "code": 0,
  "message": "success"
}
```

### Headers:

| Name          | Type   | Required  | Description              |
|---------------|--------|-----------|--------------------------|
| Authorization | String | Yes       | Auth Key (type = Bearer) |
| x-api-key     | String | Yes       | API key                  |


## Payload: future wallet
Balance Update occurs during the following

> Payload

```json
{
  "data": {
    "asset": "USDT",
    "free": "9981.51952661",
    "locked": "18.48047339"
  },
  "stream": "future_wallet",
  "eventTime": 1700703707123
}
```

## Payload: future order
Orders are updated with the executionReport event.

- direction
  - OPEN
  - CLOSE
- type
  - MARKET
  - LIMIT
  - TAKE_PROFIT
  - STOP_LOSS
  - LIQUIDATION
- status
  - PARTIAL
  - CANCELLED
  - FILLED
  - TRADING
- tif
  - GTC
  - IOC
  - FOK

> Payload

```json
{
  "data": {
    "orderId": "C171558199502193",
    "ticker": "XRPUSDT",
    "direction": "OPEN",
    "type": "LIMIT",
    "price": 0.5155,
    "amount": 2,
    "tradedAmount": 0,
    "value": 0,
    "status": "TRADING",
    "createdTime": 1715581995021,
    "canceledTime": null,
    "completedTime": null
  },
  "stream": "future_order",
  "eventTime": 1700703548846
}
```

## Payload: future position
Position are updated with the executionReport event.

- position
  - BUY
  - SELL
- status
  - USER_CLOSE
  - FORCE_CLOSE
  - TAKE_PROFIT
  - STOP_LOSS

> Payload

```json
{
  "data": {
    "ticker" : "XRPUSDT",
    "marginMode" : "ISOLATED",
    "positionMode" : "ONEWAY",
    "position" : "BUY",
    "status" : "OPEN",
    "leverage" : "10",
    "price" : "0.5155",
    "amount" : "1",
    "value" : "0.5155",
    "liquidPrice" : "0.5155",
    "unpnl" : "0",
    "createdTime" : 1700703548846,
    "closeTime" : "null",
  },
  "stream": "future_position",
  "eventTime": 1700703548846
}
```
