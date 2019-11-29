**Traditional Queue**: It works mainly on queue data structure.(FIFO). Messages will be delivered in an order. 

**Disadvantages**: 
1. ***NO Replay***: Traditional queues works on Queue. So if the message read , then messages will be deleted from queue. We can't 
replay the message
2. ***No horizantal scaling***: There is no option to increase consumers. means if we increase consumers, messages will be 
distributes across consumers, So in-turn ordering will be missed.

**Kafka**: Kafka handles this situation in ***better way*** . Its designed to work on publisher subscriber model. i.e messages 
will be delivered to all of its subscribers. Kafka works on pull based model...

1. ***Replay***: If the consumer has mulitple consumer groups, then messages will be replayed for each consumer- group. 
2. ***Parallism*** (Horizantal scaling): If the consumer maintains same consumer group name, then messages will be distributed
across all the client machines. So it shares the load
3. ***Order***: Kafka architecture maintains messages in partitional log files. Order is guranteed only if the messages are 
pushed to same partition. Producer will have flexibitly to choose partition. if 


**Advantages of Kafka**:

1. **High-throughput** :
     Kafka is capable of handling high-velocity and high-volume data using not so large hardware. It is capable of supporting message throughput of thousands of messages per second.

2. **Distributed** :
     The distributed architecture of Kafka makes it scalable using capabilities like replication and partitioning.

3. **Low Latency** :
     It is capable of handling these messages with the very low latency of the range of milliseconds, demanded by most of the new use cases.

4.  **Scalability** :
     Without incurring any downtime on the fly by adding additional nodes, Kafka can be scaled-out. Moreover, inside the Kafka cluster, the message handling is fully transparent and these are seamless.

5.  **Fault-Tolerant** :
     One of the best advantages is Fault Tolerance. There is an inherent capability in Kafka, to be resistant to node/machine failure within a cluster.

6. **Durability** :
     Here, durability refers to the persistence of data/messages on disk. Kafka uses Distributed commit log which means messages persists on disk as fast as possible, hence it is durable.

7. **High Concurrency** :
     Apache Kafka is able to handle thousands of messages per second and that too in low latency conditions with high throughput. In addition, it permits the reading and writing of messages into it at high concurrency.

8. **Consumer Friendly** :
     It is possible to integrate with the variety of consumers using Kafka. The best part of Kafka is, it can behave or act differently according to the consumer, that it integrates with because each customer has a different ability to handle these messages, coming out of Kafka. Moreover, Kafka can integrate well with a variety of consumers written in a variety of languages.

9. **Real-Time Handling** :
     Kafka can handle real-time data pipeline. Since we need to find a technology piece to handle real-time messages from applications, it is one of the core reasons for Kafka as our choice.

10. ***Better balance of CAP theorem***: 
  
      1. ***High Availability***: As it can with stand n-1 failures, So kafka cluster will be highly available to publish the messages
  to its consumers
  
    2. ***Partition Tolerence***:  If topic is configured with N replicators, then it can withstand N-1 failures. So even one broker
  failure, there wont be any outage. Message will be published to consumers without any interuption 
 
    3. ***Consistency***: Consistency means maintaining same copy across all its replications. If the transaction fails, then
  half messages should not be updated to replications. Entire transction will be rolled back. Kafka provides options (ACKS) to producer
  to achieve this. If the user chooses to ACKS = ALL, then leader will wait until acknowledgement by each of its replica.

**Dis-Advantages of Kafka**:
  1. **No Complete Set of Monitoring Tools** :
      Kafka doesn’t have complete set of management and monitoring tools, so Startup companies fear to use Kafka for long run.

  2. **Not support wildcard topic selection** :
      There is an issue that Kafka only matches the exact topic name, that means it does not support wildcard topic selection.        Because that makes it incapable of addressing certain use cases.
      
  3. **Reduces Performance** :
      In general, there are no issues with the individual message size. However, the brokers and consumers start compressing          these messages as the size increases. Due to this, when decompressed, the node memory gets slowly used. Also, compress        happens when the data flow in the pipeline. It affects throughput and also performance. 

  4. **Behaves Clumsy**:
      Sometimes, it starts behaving a bit clumsy and slow, when the number of queues in a Kafka cluster increases. 
  
  5. **No order guarantee**:
      Kafka maintains order across partition level only. So if the producers delivers the message across different paritions,       then there wont be any order guarantee. 

**Kafka vs Rabbit MQ**: 
https://jack-vanlightly.com/blog/2017/12/4/rabbitmq-vs-kafka-part-1-messaging-topologies
