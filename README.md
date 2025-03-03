# MQTT_in_react
Implement MQTT in react application

<p align="center" width="100%">
    <img width="30%" src="https://github.com/jkaewprateep/MQTT_in_react/blob/main/python-logo.jpg">
    <img width="20%" src="https://github.com/jkaewprateep/MQTT_in_react/blob/main/mqtt.jpg">
    <img width="8.3%" src="https://github.com/jkaewprateep/MQTT_in_react/blob/main/image21.jpg">
    <img width="18.9%" src="https://github.com/jkaewprateep/MQTT_in_react/blob/main/kid_17.jpg"> </br>
    <b> Implement MQTT in react application </b> </br>
    <b> ( Picture from Internet ) </b> </br>
</p>

🧸💬 Publisher  Subscriber broadcast message useful for communication from a single source to multiple subscribers and the property of this communication is safe the message continues to grow very fast since the publisher answers subscribers with similar and different channels by their selection. It can communicate within the secured channel of WebSocket ```wss://``` and implement user credentials, We use with our react application </br>
🐑💬 ➰ Repeating information and saving a lot of bandwidth for all client requests from third-party sources for the same information when one single publisher is working for this path of the solution. Within secured communication how often does authentication or time limit prevent someone in the same network from acting as our solution subscriber and also client activity or prolong the connectivity for streaming information receving? </br>

🦭💬 Implementing is easy as broadcast news channel part of information can read and path of information need to extract and transform, in this example had an example of transform information to display on our react application. Do not forget feeding information is needed for both side's expectations to have a sentence comparison or reading from extracted information should lead to full understanding. </br>

🐯💬 Culture-INFO, We borrow the communication from both Polygon and Alpaca we reserve the name for understanding and someone who changes the message subscriber knows about the objective and resources of our news publisher. </br>
🦁💬 The maintenance list should be provided and name codes should be identified, labeled, and noticed by observation in this example is Polygon and Alpaca. The name noticed cannot identify the source will have a secondary order and be considered to be purged from the system then labels of the communication channel subscriber make secured communication and easy for maintenance and services.</br>

### Codings example
🐐💬 It is simple to subscribe service that the publisher published and allowed by the IT networks administrator, the re-connection time period is a sample policy for recognizing subscribers who are subscribed to the service to prevent third-party extract information from living longer in the network. </br>   
```
const MQTT_WEBSOCKET_URL = "ws://tg-stocks-broker.techglobetrading.com:8083/mqtt";
    const TOPICS = ["tg/polygon/QCOM", "tg/polygon/SMCI", "tg/polygon/TSLA", "tg/polygon/AMZN", "tg/polygon/GOOGL", "tg/polygon/META",
        "tg/polygon/TQQQ", "tg/polygon/AAPL", "tg/polygon/AMD","tg/polygon/COIN", "tg/polygon/CRWD", "tg/polygon/SQQQ",
        "tg/polygon/MSFT", "tg/polygon/MSTR", "tg/polygon/NFLX", "tg/polygon/NVDA"];

    useEffect(() => {
        const client = mqtt.connect(MQTT_WEBSOCKET_URL, {
            clean: true,
            connectTimeout: 4000,
            reconnectPeriod: 1000,
        });

        client.on("connect", () => {
            console.log("Connected to MQTT Broker (WebSocket)");
            client.subscribe(TOPICS, (err) => {
                if (err) {
                    console.error("Subscribe error:", err);
                } else {
                    console.log("Subscribed to topics:", TOPICS);
                }
            });
        });

        client.on("message", (topic, message) => {
            const payload = JSON.parse(message.toString());
            console.log(`Received from ${topic}:`, payload);

            setMessages((prevMessages) => {
                const existingIndex = prevMessages.findIndex(stock => stock.symbol === payload.symbol);
                
                if (existingIndex !== -1) {
                    return prevMessages.map((stock, index) =>
                        index === existingIndex ? { ...stock, ...payload } : stock
                    );
                } else {
                    return [...prevMessages, payload];
                }
            });
        });

        client.on("error", (err) => {
            console.error("MQTT Error:", err);
        });

        return () => {
            client.end();
        };
    }, []);
```
👧💬 🎈 Pretty easy to implement when information is in a Java array, mapping function. Should the price be added to this subscription? </br>
```
<table className="w-full mt-2 border">
                            <thead>
                                <tr className="bg-gray-300">
                                    <th className="p-2">Stock Name</th>
                                    <th className="p-2">Amount</th>
                                    <th className="p-2">Trend</th>
                                </tr>
                            </thead>
                            <tbody>
                            {messages.length > 0 ? (
                                messages.map((stock, index) => (
                                    <tr key={stock}>
                                        <td className="p-2">{stock.symbol}</td>
                                        {/* <td className="p-2">{stock.volume}</td> */}
                                        <td
                                            className={`p-2 ${
                                                stock.close >= stock.open ? 'text-green-500' : 'text-red-500'
                                            }`}
                                        >
                                            {stock.volume}
                                        </td>
                                        <td
                                            className={`p-2 ${
                                                stock.close >= stock.open ? 'text-green-500' : 'text-red-500'
                                            }`}
                                        >
                                            {stock.close >= stock.open ? "▲ Up" : "▼ Down"}
                                        </td>
                                    </tr>
                                ))
                            ) : (
                                <tr>
                                    <td colSpan={3} className="text-center p-4">
                                        Waiting for data...
                                    </td>
                                </tr>
                            )}
                            </tbody>
                        </table>
```

---

<p align="center" width="100%">
    <img width="30%" src="https://github.com/jkaewprateep/advanced_mysql_topics_notes/blob/main/custom_dataset.png">
    <img width="30%" src="https://github.com/jkaewprateep/advanced_mysql_topics_notes/blob/main/custom_dataset_2.png"> </br>
    <b> 🥺💬 รับจ้างเขียน functions </b> </br>
</p>
