# Spot Websocket User Stream

- The base API endpoint is: ```https://openapi.bitmusa.com```
- A User Data Stream listenKey is valid for 60 minutes after creation.
- Doing a PUT on a listenKey will extend its validity for 60 minutes.
- Doing a DELETE on a listenKey will close the stream and invalidate the listenKey.
- Doing a POST on an account with an active listenKey will return the currently active listenKey.
- A listenKey is a stream.
- The base websocket endpoint is: ```wss://websocket.bitmusa.com:60002```
- User Data Streams are accessed at /ws/spot/<listenKey>
- A connection to only valid for 24 hours; expect to be disconnected at the 24 hour mark.

## Spot ListenKey

### Spot Create ListenKey

```POST /spot/userDataStream```

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

### Spot Keep-alive ListenKey

```PUT /spot/userDataStream```

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

### Spot Close ListenKey

```DELETE /spot/userDataStream```

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


## Payload: spot wallet
Balance Update occurs during the following

> Payload

```json
{
  "data": {
    "asset": "USDT",
    "free": "1132800.449",
    "locked": "80669.91"
  },
  "stream": "spot_wallet",
  "eventTime": 1700703548846
}
```

## Payload: spot order
Orders are updated with the executionReport event.

- direction
  - BUY
  - SELL
- type
  - MARKET_PRICE
  - LIMIT_PRICE
- status
  - TRADING
  - COMPLETED
  - CANCELED
  - OVERTIMED

> Payload

```json
{
  "data": {
    "orderId": "C171558199502193",
    "symbol": "XRP/USDT",
    "direction": "BUY",
    "type": "LIMIT_PRICE",
    "price": 0.5155,
    "amount": 2,
    "tradedAmount": 0,
    "value": 0,
    "status": "TRADING",
    "createdTime": 1715581995021,
    "canceledTime": null,
    "completedTime": null
  },
  "stream": "spot_order",
  "eventTime": 1700703548846
}
```
