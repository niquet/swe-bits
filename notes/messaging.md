# Messaging
- Key concept in several architectural styles, including event-driven architecture (EDA), microservices, and message driven-architecture (MDA) [1]
- Powerful concept that allows for decoupling and scalability of systems and it's used in different architectural styles to improve the flexibility and scalability of the system by allowing for loose coupling between components and making it easier to add new features or modify existing ones [1]

---

- Message: exchange of information between a sender and one or many receivers [2]
- **Message exchange architectures:** messaging patterns that are relevant to the mechanism for transmitting messages between a sender and receiver [2]
  - **Pub-Sub**
    - Publisher sends a message to a topic (much like an inbox) on a message broker [2]
    - Different implementations have different names for the concept of a _topic_ (RabitMQ calls it _Exchange_, Kafka calls it a _Topic_)
    - Subscriber binds to the topic and receives messages from the topic in an asynchronous manner [2]
    - Messages in the Pub-Sub pattern tend to be discrete, containing all the information that a process needs to act upon the data provided [2]
    - Benefits
      - Message in, message out [2]
      - Asynchronicity: no blocking lock between sender and receiver [2]
      - Receiver accepts messages at its convenienve [2]
    - Pub-Sub pattern is well-suited for providing event information to interested parties [2]
  - **Fanout**
    - Similar to Pub-Sub: interested party binds to a topic [2]
    - Differnt from Pub-Sub: many interested  parties will bind to a given topic [2]
    - When a message is sent to a topic, all subscribers will receive a copy of the message sent to the topic (i.e. the message is "fanned out") [2]
    - Fanout pattern sends a copy of a message to all interested subscribers [2]
    - Example: Twitter; a tweet is sent to all the parties following the person sending the tweet [2]
  - **Unidirectional streaming**
    - Sender emits data continuously to a receiver [2]
    - Sender might be a service that has direct knowledge of the recevier or a sender might be connected to a broker technology that in turn forwards the stream via some sort of topic mechanism [2]
    - Receivers bound to a topic on the broker receive a continuous flow of messages accordingly [2]
    - Apache Kafka is an example of a message broker technology that implements unidirectional streaming [2]
  - **Bidirectional streaming**
    - A continuous flow of messages is sent between sender and receiver as well as between reveiver and sender (data continuously flows between server and receiver in both directions) [2]
    - An example of bidirectional streaming is gRPC
    - gRPC runs under HTTP/2, which allows a sender to establish a constant connection to a receiver [2]
    - Once connected, data can flow back and forth between sender and receiver in a continuous stream [2]
- **Routing:** messaging patterns that describe the dfferent ways to route messages between a sender and a receiver [2]
  - **Unicast**
    - Messages get routed from a sender to a designated/single receiver [2]
    - Example: HTTP request/response exchange
  - **Broadcast**
    - Sender emits a message to all receivers on the network [2]
    - 
- Pub-Sub, Fanout, and Streaming patterns focus on the architecture of data transmission [2]
- Unicast, Broadcast, Multicast, and Anycast patterns focus on routing [2]

## Amazon Simple Queue Service (SQS)
- 

## Credits
[1] https://roadmap.sh/software-design-architecture
[2] https://www.redhat.com/architect/architectural-messaging-patterns
