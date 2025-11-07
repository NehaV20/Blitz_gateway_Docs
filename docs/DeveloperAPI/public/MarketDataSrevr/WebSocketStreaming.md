# WebSocket Streaming 

## Overview

The **WebSocket Streaming API** allows real-time streaming of market data for various financial instruments. Using this API, users can receive up-to-date information such as instrument prices, market depth, index data, and more. This API uses WebSocket for a continuous connection, providing a high-frequency data stream.

---

## Endpoint

| Method | URL                                               |
|--------|----------------------------------------------------|
| GET    | `/streaming/ws?key={ACESS-TOKEN}`                      |

---

## Headers

| Header        | Value             | Required |
|---------------|-------------------|----------|
| Content-Type  | application/json  | Yes      |
| Accept        | */*               | Yes      |

---

## WebSocket Message Format

The WebSocket connection supports various message types, including requests to subscribe or unsubscribe to market data, as well as real-time updates.

### Subscribe Message Format

To subscribe to market data for a specific instrument, send the following message format:

```json
{
  "action": "subscribe",  // or "unsubscribe" to stop receiving data
  "instrumentIds": [
    "1010010002000001"
  ]
}
```
action: "subscribe" to begin receiving data, or "unsubscribe" to stop.

instrumentIds: A list of instrument IDs for which data is requested.


## WebSocket message formats:
[marketdata.proto](/marketdata.proto)
## WebSocket Response

Market Depth Message 

```json
{
  "MessageCode": 1502,
  "ID": 1010010002000001,
  "MarketDepthMessage": {
    "InstrumentID": 1010010002000001,
    "ExchangeSegment": "NSECM",
    "InstrumentName": "NIFTY 50",
    "LTP": 17750.25,
    "LTQ": 100,
    "LTT": 1652496100,
    "BestBidLevel": [
      {
        "Qty": 500,
        "Price": 17740.00,
        "Orders": 10
      }
    ],
    "BestAskLevel": [
      {
        "Qty": 1000,
        "Price": 17760.00,
        "Orders": 15
      }
    ]
  }
}

```

Index Data Message

```json
{
  "MessageCode": 1505,
  "IndexDataListMessage": {
    "IndexDataList": [
      {
        "InstrumentID": 1010010003000001,
        "ExchangeSegment": "NSECM",
        "IndexName": "NIFTY 50",
        "Last": 17750.25,
        "Open": 17700.00,
        "High": 17800.00,
        "Low": 17650.00,
        "Close": 17725.00,
        "YearlyHigh": 18000.00,
        "YearlyLow": 17000.00,
        "NetChangeIndicator": 1
      }
    ]
  }
}
```
## WebSocket Event Handling
<pre>
```
import * as protobuf from "protobufjs";

const decoder = await protobuf.load("message.proto");
const socket = new WebSocket(`${marketDataUrl}?key=${marketDataApiToken}`);

socket.onmessage = (event: MessageEvent) => {
  if (decoder !== null) {
    try {
      const base64Data = event.data;
      //  console.log(base64Data);
      const buffer = base64ToUint8Array(base64Data);
      //  console.log(buffer.MessageCode);
      const decodedMessage = decoder.decode(buffer);
      //  if messageCode == 1502  then decode using
      const messageObj: any = decoder.toObject(decodedMessage, {
        longs: String,
        enums: String,
        bytes: String,
      });
  
      switch (messageObj.MessageCode) {
        case 1502: // tradable instrument
          socketDataBuffer.set(messageObj.ID, messageObj);
          console.log(messageObj.MarketDepthMessage); // Here is the instrument data.
          break;
        case 1505: // index instrument
          let indexData = messageObj?.IndexDataListMessage?.IndexDataList;
          let formattedData: SocketData[] = indexData.map((item: any) => {
            let ret = {
              ID: item?.InstrumentID,
              stockIndexData: item,
              MessageCode: messageObj.MessageCode,
            }
            return ret;
          });
          console.log(formattedData);  // Here is the instrument data.
          break;
      }
    } catch (e: any) {
      // console.error("Error decoding message:", e);
    }
  }
}
```
</pre>

## Message Codes

| Code | Message Type             |
|------|---------------------------|
| 1502 | Market Depth Message     |
| 1505 | Index Data List Message  |


