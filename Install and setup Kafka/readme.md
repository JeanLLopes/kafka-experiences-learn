**Download**
- https://kafka.apache.org/downloads
- Pre-reqs
  - Java 8 (exacly this version)   


## **Install on MAC OS**

Mac OS X - Summary
In summary, for Mac OS X
Install brew if needed: /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

Download and Setup Java 8 JDK:

brew tap caskroom/versions
brew cask install java8
Download & Extract the Kafka binaries from https://kafka.apache.org/downloads

Install Kafka commands using brew: brew install kafka

Try Kafka commands using kafka-topics (for example)

Edit Zookeeper & Kafka configs using a text editor

zookeeper.properties: dataDir=/your/path/to/data/zookeeper

server.properties: log.dirs=/your/path/to/data/kafka

Start Zookeeper in one terminal window: zookeeper-server-start config/zookeeper.properties

Start Kafka in another terminal window: kafka-server-start config/server.properties

<br>

<br>

## **Install on Linux**

Linux - Summary
In summary, for Linux (ex: Ubuntu)
Download and Setup Java 8 JDK:

sudo apt install openjdk-8-jdk
Download & Extract the Kafka binaries from https://kafka.apache.org/downloads

Try Kafka commands using bin/kafka-topics.sh (for example)

Edit PATH to include Kafka (in ~/.bashrc for example) PATH="$PATH:/your/path/to/your/kafka/bin"

Edit Zookeeper & Kafka configs using a text editor

zookeeper.properties: dataDir=/your/path/to/data/zookeeper

server.properties: log.dirs=/your/path/to/data/kafka

Start Zookeeper in one terminal window: zookeeper-server-start.sh config/zookeeper.properties

Start Kafka in another terminal window: kafka-server-start.sh config/server.properties

Important: For the rest of the course, don't forget to add the extension .sh to commands being run

<br>

<br>

## **Install on Windows**

In summary, for Windows
NOTE: Kafka 3.0 has a bug for Windows, either use Kafka 2.8 or wait for Kafka 3.0.1 or Kafka 3.1.0 (https://issues.apache.org/jira/browse/KAFKA-13391)

Download and Setup Java 8 JDK

Download the Kafka binaries from https://kafka.apache.org/downloads

Extract Kafka at the root of C:\

Setup Kafka bins in the Environment variables section by editing Path

Try Kafka commands using kafka-topics.bat (for example)

Edit Zookeeper & Kafka configs using NotePad++ https://notepad-plus-plus.org/download/

zookeeper.properties: dataDir=C:/kafka_2.12-2.0.0/data/zookeeper (yes the slashes are inversed)

server.properties: log.dirs=C:/kafka_2.12-2.0.0/data/kafka (yes the slashes are inversed)

Start Zookeeper in one command line: zookeeper-server-start.bat config\zookeeper.properties

Start Kafka in another command line: kafka-server-start.bat config\server.properties



Important: For the rest of the course, don't forget to add the extension .bat to commands being run


<br>

<br>

<br>

<br>


**Please refer to this lecture first if you have setup problems.**
=====================

> Zookeeper - java.net.BindException: Address already in use

Something is already occupying your port 2181. Figure out which application it is and stop it

> Kafka - org.apache.kafka.common.KafkaException: Socket server failed to bind to 0.0.0.0:9092: Address already in use.

Something is already occupying your port 9092. Figure out what it is and stop it.
Otherwise, if you really insist, you can change the Kafka port by adding the following line to server.properties

<br>

# example for port 9093
listeners=PLAINTEXT://:9093
> My topics are losing their data after a while

This is how Kafka works. Data is only retained for 7 days.

> The topics list is disappearing

Make sure you have changed the Zookeeper dataDir=/path/to/data/zookeeper , and Kafka log.dirs=/path/to/data/kafka

> I have launched Kafka in a VM or in the Cloud, and I can't produce to Kafka

If you can't produce to Kafka, it's possible you are using a VM and this can break the Kafka behaviour. Please look at the annex lectures for solutions of how to deal with that. I strongly recommend doing this tutorial using the Kafka binaries and localhost

