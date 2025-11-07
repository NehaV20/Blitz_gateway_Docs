## Protobuf Decoding
 The Market Data Fedd responses are delivered in **binary  Protobuf Format**. to interpret the incoming straem , you must use the provided [marketdata.proto](/marketdata.proto)
 defintin and and compile in into the corresponding language specific classes.

## Decoding Market Feed 
Since the web socket stram sends deta in serialized Protobuf format decoding is essential before acessing individual fielde like LTP, Price, Orders.

# Steps to Decode 

## 1. Obtain the ProtoFile 

Use the official **marketdata.proto** file .
## 2. Generate Class

Use the Protobuf complier(**protoc**) to genrate calsess.

**Python**:
```python
protoc --python_out=. marketdata.proto
```
## Integrate Into SDK
Import the generated classes and use them to decode the incoming byte stream:

Python:
```json
def on_message(self, ws, message):
        try:
            decoded = base64.b64decode(message)
            md_message = marketdata_pb2.MarketDataMessageBase()
            md_message.ParseFromString(decoded)

            if md_message.MessageCode == 1502:
                logging.info(f"[MarketDepth] {md_message.MarketDepthMessage}")
            elif md_message.MessageCode == 1505:
                for idx in md_message.IndexDataListMessage.IndexDataList:
                    logging.info(f"[Index] {idx}")
        except Exception as e:
            logging.error(f"Failed to parse WebSocket message: {e}")

    def on_error(self, ws, error):
        logging.error(f"WebSocket Error: {error}")

    def on_close(self, ws, close_status_code, close_msg):
        logging.warning(f"WebSocket closed: {close_status_code}, {close_msg}")
```

> **Note**: The `.proto` file can be compiled in any language that supports Protobuf  
> (e.g., Python, C++, Java, Kotlin, C#, Go, etc.) using the official `protoc` compiler.

