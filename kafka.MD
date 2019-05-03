**Traditional Queue**: It works mainly on queue data structure.(FIFO). Messages will be delivered in an order. 

**Disadvantages**: 
1. ***NO Replay***: Traditional queues works on Queue. So if the message read , then messages will be deleted from queue. We can't 
replay the message
2. ***No horizantal scaling***: There is no option to increase consumers. means if we increase consumers, messages will be 
distributes across consumers, So in-turn ordering will be missed.

**Kafka**: Kafka handles this situation in ***better way*** . Its designed to work on publisher subscriber model. i.e messages 
will be delivered to all of its subscribers

1. ***Replay***: If the consumer has mulitple consumer groups, then messages will be replayed for each consumer- group. 
2. ***Parallism*** (Horizantal scaling): If the consumer maintains same consumer group name, then messages will be distributed
across all the client machines. So it shares the load
3. ***Order***: Kafka architecture maintains messages in partitional log files. Order is guranteed only if the messages are 
pushed to same partition. Producer will have flexibitly to choose partition. if 

**Operational Advantages**: 

1. ***Distribution***: Kafka copies the data across all its replicator. So even if the one broker goes down, messages will be 
read from other broker. if topic is configured with N replicators, then it can withstand N-1 failures
2. ***Better balance of CAP theorem***: 
  a. ***High Availability***: As it can with stand n-1 failures, So kafka cluster will be highly available to publish the messages
  to its consumers
  b. ***Partition Tolerence***:  If topic is configured with N replicators, then it can withstand N-1 failures. So even one broker
  failure, there wont be any outage. Message will be published to consumers without any interuption 
  c. ***Consistency***: Consistency means maintaining same copy across all its replications. If the transaction fails, then
  half messages should not be updated to replications. Entire transction will be rolled back. Kafka provides options (ACKS) to producer
  to achieve this. If the user chooses to ACKS = ALL, then leader will wait until acknowledgement by each of its replica.
  
**Kafka vs Rabbit MQ**: 
https://jack-vanlightly.com/blog/2017/12/4/rabbitmq-vs-kafka-part-1-messaging-topologies
