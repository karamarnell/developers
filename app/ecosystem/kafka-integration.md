---
id: page-plugin
title: Qordoba - Apache Kafka integration 
header_title: Qordoba - Apache Kafka integration 
header_icon: /assets/images/icons/plugins/kafka-integration.png
breadcrumbs:
  Plugins: /plugins
nav:
  - label: Getting Started
    items:
      - label: Requesting Access
---
Qordoba can consume and fetch data from Apache Kafka, We can also send content from the Qordoba workflow as a message to Apache Kafka. The messages may be individual segment or may be delimited, using a user-specified delimiter, such as a new-line. 

```
This integration specifically for 0.8.x versions (Kafka 0.9.x. Kafka 0.10.x available as beta)
```
In the tables below, you can view which parameters you can use to customize your configuration with this particular system:

```
'ZooKeeper Connection String'	The Connection String to use in order to connect to ZooKeeper. This is often a comma-separated list of <host>:<port> combinations. For example, host1:2181,host2:2181,host3:2188
'Topic Name'	The Kafka Topic to pull messages from
'ZooKeeper Commit Frequency'	Specifies how often to communicate with ZooKeeper to indicate which messages have been pulled. A longer time period will result in better overall performance but can result in more data duplication if a NiFi node is lost #the default value is 60 seconds
'Batch Size'	Specifies the maximum number of messages to combine into a single FlowFile. These messages will be concatenated together with the <Message Demarcator> string placed between the content of each message. If the messages from Kafka should not be concatenated together, leave this value at 1. #the default value is 1
'Message Demarcator'	Specifies the characters to use in order to demarcate multiple messages from Kafka. If the <Batch Size> property is set to 1, this value is ignored. Otherwise, for each two subsequent messages in the batch, this value will be placed in between them. #the default value is \n
'Client Name'	Client Name to use when communicating with Kafka #the default value is NiFi-mock-processor
'Group ID'	A Group ID is used to identify consumers that are within the same consumer group #the default value is mock-processor
'Kafka Communications Timeout' The amount of time to wait for a response from Kafka before determining that there is a communications error #the default value is 30 secs
'Zookeeper Communications Timeout'	The amount of time to wait for a response from ZooKeeper before determining that there is a communications error #the default time is 30 secs
'Auto Offset Rest'	Automatically reset the offset to the smallest or largest offset available on the broker #the default value is largest
```

```
'Known Brokers'	A comma-separated list of known Kafka Brokers in the format <host>:<port>
'Topic Name'	The Kafka Topic of interest
'Partition Strategy'	Specifies how messages should be partitioned when sent to Kafka #the default value is Round Robin
'Partition'	Specifies which Kafka Partition to add the message to. If using a message delimiter, all messages in the same FlowFile will be sent to the same partition. If a partition is specified but is not valid, then all messages within the same FlowFile will use the same partition but it remains undefined which partition is used.
'Kafka Key'	The Key to use for the Message
'Delivery Guarantee' Specifies the requirement for guaranteeing that a message is sent to Kafka #the default value is 0
'Message Delimiter'	Specifies the delimiter (interpreted in its UTF-8 byte representation) to use for splitting apart multiple messages within a single FlowFile. If not specified, the entire content of the FlowFile will be used as a single message. If specified, the contents of the FlowFile will be split on this delimiter and each section sent as a separate Kafka message. Note that if messages are delimited and some messages for a given FlowFile are transferred successfully while others are not, the messages will be split into individual FlowFiles, such that those messages that were successfully sent are routed to the 'success' relationship while other messages are sent to the 'failure' relationship.
'Max Buffer Size'	The maximum amount of data to buffer in memory before sending to Kafka #the default value is 5 MB
'Max Record Size'	The maximum size that any individual record can be. #the default value is 1 MB
'Communications Timeout'	The amount of time to wait for a response from Kafka before determining that there is a communications error #the default value is 30 seconds
'Batch Size'	This configuration controls the default batch size in bytes.The producer will attempt to batch records together into fewer requests whenever multiple records are being sent to the same partition. This helps performance on both the client and the server. #the default value is 16384
'Queue Buffering Max Time' Maximum time to buffer data before sending to Kafka. For example a setting of 100 ms will try to batch together 100 milliseconds worth of messages to send at once. This will improve throughput but adds message delivery latency due to the buffering.
'Compression Codec'	This parameter allows you to specify the compression codec for all data generated by this producer. #the default value is none
'Client Name'	Client Name to use when communicating with Kafka
```
