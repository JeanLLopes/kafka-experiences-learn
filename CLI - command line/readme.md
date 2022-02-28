# **CLI**

<br>

## **CREATE TOPIC**

To create a first topic you can use the follow command line

<br>

[inside in kafka path, with CMD]

``kafka-topics --zookeeper 107.0.0.1:2181 --topic first_topic --create --partitions 3 --replication-factor 1``

To list topics use:

``kafka-topics --zookeeper 107.0.01:2181 --list``

``kafka-topics --zookeeper 107.0.01:2181 --list {topic-name} --describe``

[![image](https://www.goavega.com/wp-content/uploads/2019/12/describe-topic.png)](https://www.goavega.com/wp-content/uploads/2019/12/describe-topic.png)


## **CREATE CONSOLE PRODUCER**

To create a first producer you can use the follow command line

<br>

[inside in kafka path, with CMD]

``kafka-console-producer --broker-list 127.0.0.1:9092 --topic {topic name} {messages}``

[![image](https://www.tutorialkart.com/wp-content/uploads/2017/11/apache-kafka-console-producer-and-consumer-example.png)](https://www.tutorialkart.com/wp-content/uploads/2017/11/apache-kafka-console-producer-and-consumer-example.png)

<br>

‼ If you sent a message to a topic without exist, in second attempt Kafka Zookeeper was create a new topic for you and sent a message in this new topic
To list topics use:

‼ The recommendation is create a topic after sent a message



## **CREATE CONSOLE CONSUMER**

To create a first consumer you can use the follow command line

``kafka-console-consumer --bootstrat-server 127.0.0.1:9092 --topic first_topic --from-beginning``

> **--from-beginning** = when you insert this PARAMETER you can get the all messages sent to topic from de beginning

[![image](https://static.javatpoint.com/tutorial/kafka/images/kafka-console-consumer3.png)](https://static.javatpoint.com/tutorial/kafka/images/kafka-console-consumer3.png)


### CONSUMER BY GROUP

To create a consumer you can use the follow command line, in this case, each consumer get one message

``kafka-console-consumer --bootstrat-server 127.0.0.1:9092 --topic first_topic --group my-first-application``

> **--from-beginning** = when you insert this PARAMETER you can get the all messages sent to topic from de beginning

[![image](https://miro.medium.com/max/1400/1*gbzEqBqcfZ7WhKKVmBOJwQ.png)](https://miro.medium.com/max/1400/1*gbzEqBqcfZ7WhKKVmBOJwQ.png)






