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

