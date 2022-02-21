# OVERVIEW

### PARTITIONS and OFFSET

- Kafka works with FIFO (First in first out) by default
- You not have access to sent messages cross Particions 
- By default as created a particion 0
- By default messages kept for one week, but you can configure by unlimited time

[![image](https://www.linkpicture.com/q/03FEDE34-93EC-46C4-845C-9778989B7AA6.png.jpg)](https://www.linkpicture.com/view.php?img=LPic62121b01e4835639921783)

[![image](https://www.linkpicture.com/q/ADAF5035-808D-499D-99BF-1B05434851BA.png.jpg)](https://www.linkpicture.com/view.php?img=LPic62121b01e4835639921783)

<br>

### BROKERS

- A kafka cluster have a mutiples brokers
- each broker has a ID, with integer name
- To started, 3 brokers is OK, but big cluster have until 100 brokers
- The TOPIC and Particions 0, 1, 2 is inside the brokers

<br>

### TOPIC REPLICATIONS FACTOR

- Replication factor is a quantity replicas you have a same partition in other Kafka Brokers
- By default de same Kafka Partitions have 2 ou 3 replicas
- The Kafka partition has a Leader Partition in on Broker
- The Kafka Partition Leader is defined by Zookeeper
- The data has syncronized using a KSQL
- If Kafka Broker down the Zookeeper sent the messages automatically to Kafka Particion **ISR(in sync replica (is a second particion in other Kafka Broker))**

<br>

### PRODUCER
- When you produce a message, you can choose if enable acknowledgment to write data on Kafka Cluster
  - Producer can use a follow options to guarantee the data write
    - ACKS = 0    => The producer not wait the data acknowledgment by Kafka Cluster (possible data loss)
    - ACKS = 1    => The producer wait for the Kafka Partition Leader data acknowledgment by Kafka Cluster (limited data loss)
    - ACKS = ALL  => The producer wait for the Kafka Partition Leader and Kafka Partition replicas data acknowledgment by Kafka Cluster (no data loss)     

- You can sent a Message Key, with a message key you can guarantee that the message are send for the same Kafka Partition
  - Example, if you send a message-key = Id_1 or Id_2, this messages are available in Kafka Broker 001, but if you send a message-key = Id_5 or Id_6, this messages are available in Kafka Broker 002, this messages not pass by Kafka round robin
  - If you not send a message-partition your message are sent to Kafka Round-Robin and the same message are available in all Kafka Broker, Kafka Round-Robin sent the message for all Kafka Brokers 
