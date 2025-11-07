Market data feed is areal-time stream of trading such as price , updates, quotes. the market data feed enables traders and system to recive timaly updates about financial instruments for desison-making and execution. it oprates over a websocket connection , ensuring low latency dilivery suitable for tarding system.

## WebSocket Authentication
To establish a WebSocket connection for real-time market data streaming, you must first authenticate your application. This involves generating an access token using the login API [AppLogin](AppLogin). Once you have the access token, it is appended to the WebSocket URL as a query parameter in the format:

```json
ws://<port>/streaming/ws?key={access_token}
```

After logging in with your credentials and generating the access token, you can use it to authorize your WebSocket connection and start receiving real-time market data.



when websocket coneected, the market data feed response requires decoding using protobuf

For more information about market data, check out the [Protobuf Decoding](ProtobufDecoding).

To integrate the WebSocket connection, you need to connect to the provided WebSocket endpoint using the **ws:** protocol. After you authenticate, your WebSocket client must be able to automatically follow any redirection to a new WebSocket endpoint.

