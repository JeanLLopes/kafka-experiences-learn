<<<<<<< HEAD
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

<br>

### CONSUMER
- Each consumer read one Kafka partition
- Consumer group is per example your application, your application have a one or more consumers 
[![image](https://www.oreilly.com/library/view/kafka-the-definitive/9781491936153/assets/ktdg_04in05.png)](https://www.oreilly.com/library/view/kafka-the-definitive/9781491936153/assets/ktdg_04in05.png)

- If your application have more consumers than Kafka Partition your consumer stay stoped
[![image](https://www.fatalerrors.org/images/blog/a0989ce8eda8a0349fa1d5bf12cb8bd6.jpg)](https://www.fatalerrors.org/images/blog/a0989ce8eda8a0349fa1d5bf12cb8bd6.jpg)

<br>

### CONSUMER OFFSET
[![image](https://ibm-cloud-architecture.github.io/refarch-eda/static/75701f1ef05216ee0b2dab14e2541f68/3cbba/consumer-groups.png)](https://ibm-cloud-architecture.github.io/refarch-eda/static/75701f1ef05216ee0b2dab14e2541f68/3cbba/consumer-groups.png)

- You can consume messages at 3 ways:
  - At most once
  - At least once
  - Exactly once
    - This is the best use, but you need a Kafka consumer to Kafka or a directy database, for example Spark Database
    - Kafka workflow or Kafka Streams API
  - [![image](https://www.singlestore.com/images/cms/blog-posts/img_blog_post_image_exactly-once-semantics-with-apache-kafka_1.jpg )](https://www.singlestore.com/images/cms/blog-posts/img_blog_post_image_exactly-once-semantics-with-apache-kafka_1.jpg )


<br>

### BROKER DISCOVERY
- When you need to connect to one broker, you will be connected to the entire cluster
- Each Kafka Broker knows about all Kafka Bokers, Kafka topics and Kafka partition
- When you connect in one Kafka Broker, the Kafka Broker sent to you metadatas about list of all Kafka Brokers
- [![image](https://miro.medium.com/max/1400/0*lsDlitjrCj7pzglr)](https://miro.medium.com/max/1400/0*lsDlitjrCj7pzglr)

<br>

### ZOOKEEPER
- Is a program separate of the Kafka
- He not talk with a Kafka consumers or Kafka producer
- Is a manager Kafka Brokers
- Kafka can not work without Zookeeper 
- Send notification to Kafka when Kafka brokers die, Kafka Brokers is comes up, delete topic, etc
- You can use more one Zookeeper, one is a Leader and others are the followers, the Zookeeper Leader comunicate with a kafka and Zookeeper followers
- [![image](https://ibm-cloud-architecture.github.io/refarch-eda/static/a87e9bc7cc0449b738232ac658865d92/2faef/kafka-hl-view.png)](https://ibm-cloud-architecture.github.io/refarch-eda/static/a87e9bc7cc0449b738232ac658865d92/2faef/kafka-hl-view.png)

<br>

### ROUNDUP
[![image](https://3.bp.blogspot.com/-zZXSxoZiG_Y/XHv3FYooSAI/AAAAAAAAAJs/57t1wWC9lGMmeBFTIiNvtH9GWegsl5oAACLcBGAs/s1600/Screen%2BShot%2B2019-03-03%2Bat%2B8.46.41%2BAM.png)](https://3.bp.blogspot.com/-zZXSxoZiG_Y/XHv3FYooSAI/AAAAAAAAAJs/57t1wWC9lGMmeBFTIiNvtH9GWegsl5oAACLcBGAs/s1600/Screen%2BShot%2B2019-03-03%2Bat%2B8.46.41%2BAM.png)


=======
>>>>>>> 3bc854c (add new module)
