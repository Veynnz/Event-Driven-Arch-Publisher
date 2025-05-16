# Module 9 Publisher

1. How much data will the publisher program send to the message broker in one run?

Looking at the main function, the publish_event function is called five times, with 5 differend user_ids and user_names. Therefore, the publisher program will send five separate messages to the message broker in one run. 



------------------------------------

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

The fact that both the publisher and the subscriber programs use the same AMQP URL (amqp://guest:guest@localhost:5672) means they are both configured to connect to the same message broker instance.

- Same Location: Both programs are trying to reach the AMQP broker running on the same machine (localhost) and listening on the same network port (5672).
- Same Authentication: Both programs are attempting to authenticate with the message broker using the same credentials (guest for both username and password).
- Communication Channel: This shared connection URL is essential for them to communicate. The publisher will send messages to this broker, and the subscriber will connect to the same broker to listen for and receive those messages.
- Loose Coupling: Even though they connect to the same broker, the publisher doesn't need to know anything specific about the subscriber, and vice versa. The message broker acts as an intermediary.

The identical URL establishes the common ground that allows the publisher to send messages to the broker, and the subscriber to receive messages from the same broker.

---

### Running RabbitMQ
![Running RabbitMQ](images/one.png)

### Subscriber - Publisher Interaction
![Subscriber - Publisher Interaction](images/two.png)

- The screenshot demonstrates successful communication between the subscriber and publisher through the RabbitMQ message broker.

- The right pane confirms the publisher executed correctly, transmitting the five distinct messages to the broker.

- The left pane illustrates the subscriber's successful reception and printout of these five messages from the publisher.

- Repeated executions of the publisher led to the subscriber receiving and displaying each set of messages, as shown in the left pane.

### Chart Spikes
![Chart Spikes](images/three.png)

The spikes shown in the chart are a representation of the running publisher program. Each execution of the publisher resulted in the sending of the 5 messages to the broker. This sudden activity resulted in the sudden increase of the "Message Rates" chart, creating the spike. Then it would go back down to 0, since no more messages are being sent. This spike would be created on every execution of the publisher.