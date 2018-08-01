# Publish-Subscribe Messaging System #

Publisher: sends messages (data) to the message queue.

Consumer: receives messages (data) from the message queue.

Topic: tag, or container with which messages are associated.

# Kafka is built on top of # 

Apache ZooKeeper: synchronization service

Apache Storm: event processor

Apache Spark: cluster-computing framework

# Components #

Topics: a stream of messages belonging to a particular category

Partition: topics may have many partitions, so it can handle an arbitrary amount of data

Partition offset: each partitioned message has a unique sequence ID called as offset

Replicas (of partition): backup of a partition to prevent data loss (no read/write)

Brokers: are responsible for maintaing the published data (may have zero or more partitions per topic)

Kafka Cluster: when more than one broker

Producers: publisher of messages to one or more Kafka topics

Consumers: read data from brokers by subscribing to one or more topics and consume published message by pulling data from the brokers.

Leader: the node responsible for all reads and writes for the given partition (every partition has one server acting as a leader).

Follower: the node which follows leader instructions

# Example #

Producers:
- producer 1
- producer 2

**writes data to**

Topics
- partition 1
- partition 2
- partition 3

Kafka Brokers
- leader
  - server 1
    - partition 1
    - replica 1
- follower 1
  - server 2
    - partition 2
    - replica 2
- follower 2
  - server 3
    - partition 3
    - replica 3

**reads data**

Consumer group
- consumer 1
- consumer 2
- consumer 3
