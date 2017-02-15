# Notes

sources

https://www.confluent.io/blog/
https://gigaom.com/2013/12/09/netflix-open-sources-its-data-traffic-cop-suro/
http://techblog.netflix.com/2016/02/evolution-of-netflix-data-pipeline.html
https://www.infoq.com/articles/apache-kafka
1) the producer can send a set of messages in a single publish request. 

2) supports both the point-to-point delivery model in which multiple consumers jointly consume a single copy of message in a queue as well as the publish-subscribe model in which multiple consumers retrieve its own copy of the message. Following code examples shows a Consumer to consume messages.

3)  If currently no message is there to consume, the iterator blocks until new messages are published to the topic. Kafka supports both the point-to-point delivery model in which multiple consumers jointly consume a single copy of message in a queue as well as the publish-subscribe model in which multiple consumers retrieve its own copy of the message.

4) Kafka has a very simple storage layout. Each partition of a topic corresponds to a logical log. Physically, a log is implemented as a set of segment files of equal sizes. Every time a producer publishes a message to a partition, the broker simply appends the message to the last segment file. Segment file is flushed to disk after configurable numbers of messages have been published or after a certain amount of time elapsed. Messages are exposed to consumer after it gets flushed.

5) Kafka brokers are stateless. This means that the consumer has to maintain how much it has consumed. Consumer maintains it by itself and broker would not do anything. Such design is very tricky and innovative in itself.

*********************
 Most importantly, how would you do these things reliably in the face of the difficulties of distributed computing such as network failures, bandwidth limitations, variable latency connections, security concerns, and anything else that can go wrong in a networked environment, perhaps even across multiple data centers? 

