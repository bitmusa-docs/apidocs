# Spot Websocket Market Stream
- The base websocket endpoint is: ```wss://websocket.bitmusa.com:60002```
- User Data Streams are accessed at /ws/spot/stream?<stream>/<stream>...
- 
## Spot Kline Stream
The Kline Streams push Kline information

| Stream Name                 | Update Speed |
|-----------------------------|--------------|
| \<symbol>@kline_\<interval> | 250ms        |

- Interval
  - 1min
  - 3min
  - 5min
  - 15min
  - 30min
  - 1H
  - 2H
  - 4H
  - 6H
  - 8H
  - 12H
  - 1D
  - 1W
  - 1M

> Payload

```json
{
  "stream": "BTCUSDT@kline_1min",
  "eventTime": 1700548317403, //event time
  "data": {
    "s": "BTC/USDT", // symbol
    "o": 29991.00000000, // openPrice
    "h": 29991.00000000, // higestPrice
    "l": 29991.00000000, // lowestPrice
    "c": 29991.00000000, // closePrice
    "t": 1700550060000, // kLine startTime
    "T": 1700548859999, // kLine endTime
    "i": "1min", // interval
    "q": 0, // total qty
    "v": 0, // total value
    "u": 1700548317403 // update time
  }
}
```

## Spot OrderBook Stream
The Kline Streams push Kline information

| Stream Name                      | Update Speed              |
|----------------------------------|---------------------------|
| \<symbol>@depth\<level>@\<Speed> | 1s or 100ms(default = 1s) |

- Level 
  - 5(default)
  - 10
  - 20

> Payload

```json
{
  "stream": "BTCUSDT@depth5@100ms",
  "eventTime": 1700548317403, //event time
  "data": {
    "updateTime": 1700549490882,
    "bids": [
      {
        "price": 29985.00,
        "amount": 0.00100
      },
      {
        "price": 29984.00,
        "amount": 0.00100
      },
      {
        "price": 29983.00,
        "amount": 0.00100
      },
      {
        "price": 29982.00,
        "amount": 0.00100
      },
      {
        "price": 29981.00,
        "amount": 0.00100
      }
    ],
    "asks": [
      {
        "price": 29987.00,
        "amount": 0.00100
      },
      {
        "price": 29988.00,
        "amount": 0.00100
      },
      {
        "price": 29989.00,
        "amount": 0.00100
      },
      {
        "price": 29990.00,
        "amount": 0.00100
      },
      {
        "price": 29991.00000000,
        "amount": 55.0953500000000000
      }
    ]
  }
}
```
