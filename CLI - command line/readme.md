## **CLI**

To create a first topic you can use the follow command line

<br>

[inside in kafka path, with CMD]

> kafka-topics --zookeeper 107.0.0.1:2181 --topic first_topic --create --partitions 3 --replication-factor 1

To list topics use:

>kafka-topics --zookeeper 107.0.01:2181 --list

>>kafka-topics --zookeeper 107.0.01:2181 --list {topic-name} --describe

[![image](https://www.goavega.com/wp-content/uploads/2019/12/describe-topic.png)](https://www.goavega.com/wp-content/uploads/2019/12/describe-topic.png)

