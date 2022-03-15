# RTM-RTC-Sample-for-comparison

## Prerequisites to reproduce the issue
must use both RTM and RTC
client must be iOS15, irreproducible with iOS14 or below

## Additional Conditions found today
- Irreproducible by limiting bandwidth/packetloss (I used Network Link Conditioner for iOS with several patterns)
- Reproducible with the Fast.com upload test
- When the issue happen, we might see the message WebSocket network error: Network process crashed.

Also I had heard that the customer is using WebSocket connection for their own Whiteboard webapp, apart from Agora.
Which seems resembles to the situation, that those Speedtesting sites also uses WebSocket connection apart from Agora.
Thus it might be said that Agora's WebSocket connection might be crash when other WS connection running outside the SDK.
