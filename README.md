# RTM-RTC-Sample-for-comparison

## Prerequisites to reproduce the issue
must use both RTM and RTC
client must be iOS15, irreproducible with iOS14 or below

## Additional Conditions found today
- Irreproducible by limiting bandwidth/packetloss (I used Network Link Conditioner for iOS with several patterns) [^1]
- Reproducible with the Fast.com upload test [^2]
- When the issue happen, we might see the message WebSocket network error: Network process crashed. [^3]

Also I had heard that the customer is using WebSocket connection for their own Whiteboard webapp, apart from Agora.
Which seems resembles to the situation, that those Speedtesting sites also uses WebSocket connection apart from Agora.
Thus it might be said that Agora's WebSocket connection might be crash when other WS connection running outside the SDK.

[^1]: 
I tested with those patterns;
- Outgoing bandwidth: 20(bps)/0
- Outgoing packetloss: 0/100
- 3G (preset)

With any configuration, I could not reproduce the issue.

[^2]: 
See the picture. After the auto-start Downlink test, you can tap on the "Show more info" button.
Then the Uplink bandwidth test starts. The issue can be reproduced when you start this uplink test.
(not when the Downlink test is going)


[^3]: 
I also found some webpages, that refers to this WebSocket connection crashes.
https://stackoverflow.com/questions/70201676/websocket-network-process-crashes-in-mobile-safari-ios-15-1-due-to-blob-creati
https://twitter.com/iCyber0n/status/1444047281028800512?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1444047281028800512%7Ctwgr%5E%7Ctwcon%5Es1_c10&ref_url=https%3A%2F%2Fzenn.dev%2Fvoluntas%2Fscraps%2F393f171bf8761d
https://github.com/gorilla/websocket/issues/731
