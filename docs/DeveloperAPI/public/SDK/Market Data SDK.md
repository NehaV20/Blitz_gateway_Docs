# Market Data SDK

*Market Data SDK* allows to interact with the market data APIs to fetch real-time market information such as LTP (Last Traded Price), Option Chain, and Quotes. It also provides WebSocket WebSocket support for subscribing to and receiving live market data.

The SDK supports authentication, fetching market data, subscribing to market feeds, and handling WebSocket connections.

---

## Features
- **Authentication**: Secure login  to obtain an **API key**. With the **API key** and **user ID** Login via [AppLogin](AppLogin) get an **Acess-Token**, we can authenticate and access the SDK.
- **Market Data APIs**:
  - Get LTP (Last Traded Price) for given instruments.
  - Get Option Chain data.
  - Get real-time quotes for instruments.
- **WebSocket Streaming**: 
  - Subscribe to live market data for specific instruments.
  - Handle real-time market depth and index updates.
- **Error Handling**: Built-in error logging and retries for WebSocket reconnections.

---

## Installation

### 1. Clone the repository:
```bash
git clone https://github.com/yourusername/market-data-sdk.git
cd market-data-sdk
```

### 2. Install dependencies:
This SDK requires Python 3.x and the `requests` and `websocket-client` libraries.

```bash
pip install -r requirements.txt
```

---

## Setup & Configuration

To start using the SDK,  need the following:
- **API Key**: With  API key to acess *SDK* and  authenticat via [AppLogin](AppLogin).
- **User ID**:  unique user identifier.

### Environment Variables (for sensitive data)
Store sensitive information, such as the API key and user ID, in environment variables for security.

```bash
export API_KEY="api-key"
export USER_ID="user-id"
```

Alternatively, can pass these directly to the client when initializing.

---

## Usage

### 1. Initialize the Client

```python
from marketdata.market_data import MarketDataClient
from marketdata.websocket_stream_handler import MarketDataWebSocketClient

client = MarketDataClient(
    app_key="app-key",
    user_id="user-id"
)
```

### 2. Authentication

*Market Data SDK* automatcally handles authentication by retrieving an access token upon initialization. The `MarketDataClient` internally calls the authentication process when the access token is needed.

### 3. Fetching Market Data

#### LTP (Last Traded Price)

To get the LTP for specific instruments:

```python
instrument_ids = [1010010002000001, 1010010002000002]
ltp = client.get_ltp(instrument_ids)
print("LTP Response:", ltp)
```

#### Option Chain

To fetch the option chain for a given symbl and expiry date:

```python
symbol = "NIFTY"
expiry_date = "20250424"
option_chain = client.get_option_chain(symbol, expiry_date)
print("Option Chain Response:", option_chain)
```

#### Quotes

To get quotes for given instruments:

```python
quote_data = client.get_quote(instrument_ids)
print("Quote Response:", quote_data)
```

---

### 4. WebSocket for Live Market Data

To subscribe to real-time market data via WebSocket:

```python

from marketdata_sdk import MarketDataClient

instrument_ids = [1010010002000001]

# Initialize Market Data Client
client = MarketDataClient(app_key="app_key", user_id= "userId")

# Connect to the WebSocket server
client.connect_ws()


# Run the client until interrupted
try:
    while True:
        time.sleep(1)
except KeyboardInterrupt:
    print("Stopping WebSocket...")
    ws_client.stop()
```

### WebSocket Methods:
- **connect_ws()**: Starts the WebSocket connection.
- **subscribe_market_data(instrument_ids)**: Subsbscribes to live market data for given instruments.
- **unsubscribe_market_data(instrument_ids)**: Unsubscribes from the market data.
- **stop_websocket()**: Stops the WebSocket connection.

---

## Advanced Usage

### Reconnection Logic:
The 8MarketDataWebSocketClien8thas automatic reconnection logic, which attempts to reconnect when the connection is lost.

### Callbacks:
can define custom callbacks for handling WebSocket events:
- **on_connect**: Callback when WebSocket connects.
- **on_close**: Callbackkk when WebSocket closes.
- **on_tick**: Callback for receiving market data ticks.
- **on_message**: The `on_message` callback is used to handle real-time data received over WebSocket. The user can assign their own function to this callback, which will be triggered every time a new WebSocket message arrives.
for more Info visit [callbackimplementation](callbackimplementation)
---

## Error Handling

The SDK includes error handling mechanisms:
- **Network errors**: Retries on WebSocket disconnections.
- **API errors**: Logs HTTP status codes and error messages.
- **Invalid data**: Logs detailed error messages when parsing issues occur.

---

## Troubleshooting

- **Connection Issues**: Ensure  API key is valid and that connected to the internet.
- **No Data Received**: Check if subscribing to the correct instrument IDs and verify the WebSocket connection is active.

---


## License

This SDK is open-source and licensed under the [MIT License](LICENSE).
