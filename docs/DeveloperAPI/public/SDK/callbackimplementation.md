 **callback mechanism** works in the **Market Data SDK**, specifically for handling WebSocket messages. This functionality allows the user to define a callback that will be executed when new messages are received via the WebSocket connection.

### 1. Defining the Callback Function

First, you need to define a function that will be called whenever new data is received. This function will process the incoming data as needed.

#### Example:

```python
def my_callback_function(data):
    print("New tick data received:", data)
```
## Setting the Callback Function
Once you have defined your callback function, you can assign it to the on_message property of the *MarketDataWebSocketClient*. This ensures that your function will be triggered when new messages are received.

```python
client.on_message = my_callback_function
```

`on_message` Property (Getter/Setter)
The on_message property is responsible for getting and setting the callback function. When you assign your callback function to this property, it is stored in the _on_tick variable, and the *MarketDataWebSocketClient* is instructed to use this function for handling incoming messages.

```python
@property
def on_message(self):
    return self._on_tick

@on_message.setter
def on_message(self, callback):
    self._on_tick = callback
    self.ws_client.set_on_message(callback)
```
## Setting the Callback 
When the callback is set, it is passed to the set_on_message method of the *MarketDataWebSocketClient*, which updates the internal callback handler.

```python
def set_on_message(self, callback):
    self.on_message_callback = callback
```
## WebSocket Message Handler
Once the WebSocket connection is established and messages are received, the WebSocket client calls the `on_message` method with the received data. This method decodes the message and, if the callback function is defined, calls it with the decoded message.
```python
def on_message(self, ws, message):
    try:
        logging.debug(f"Raw message received: {message}")
        decoded = base64.b64decode(message)
        md_message = marketdata_pb2.MarketDataMessageBase()
        md_message.ParseFromString(decoded)

        if self.on_message_callback:
            self.on_message_callback(md_message)

    except Exception as e:
        logging.error(f"Failed to parse WebSocket message: {e}")
```
