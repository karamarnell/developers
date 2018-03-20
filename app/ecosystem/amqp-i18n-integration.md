---
id: page-plugin
title: MQTT integration
header_title: Qordoba MQTT integration
header_icon: /assets/images/icons/plugins/mqtt.png
breadcrumbs:
  Plugins: /plugins
---


The Qordoba connector acts as stand-alone service and can will Subscribers/Publishes to **any configurable MQTT topic.** 
In the tables below, you can view which parameters you can use to customize your configuration with this particular system:


```javascript
`Broker URI`	The URI to use to connect to the MQTT broker (e.g. tcp://localhost:1883). The 'tcp' and 'ssl' schemes are supported. In order to use 'ssl', the SSL Context Service property must be set.
`Client ID`	MQTT client ID to use
`Username`	Username to use when connecting to the broker
`Password`	Password to use when connecting to the broker
`SSL Context Service`	The SSL Context Service used to provide client certificate information for TLS/SSL connections.
`Last Will Topic` The topic to send the client Last Will to. If the Last Will topic and message are not set then a Last Will will not be sent.
`Last Will Message`	The message to send as the client Last Will. If the Last Will topic and message are not set then a Last Will will not be sent.
`Last Will Retain`	Whether to retain the client Last Will. If the Last Will topic and message are not set then a Last Will will not be sent.
`Last Will QoS Level` QoS level to be used when publishing the Last Will Message
`Session State`	Whether to start afresh or resume previous flows. #value is true or false
`Connection Timeout`	Maximum time interval the client will wait for the network connection to the MQTT server to be established. The default timeout is 30 seconds. A value of 0 disables timeout processing meaning the client will wait until the network connection is made successfully or fails.
`Keep Alive Interval` Defines the maximum time interval between messages sent or received. It enables the client to detect if the server is no longer available, without having to wait for the TCP/IP timeout. The client will ensure that at least one message travels across the network within each keep alive period. In the absence of a data-related message during the time period, the client sends a very small "ping" message, which the server will acknowledge. A value of 0 disables keepalive processing in the client.
`Topic Filter`	The MQTT topic filter to designate the topics to subscribe to.
`Quality of Service (QoS)` The Quality of Service(QoS) to receive the message with. Accepts values '0', '1' or '2'; '0' for 'at most once', '1' for 'at least once', '2' for 'exactly once'.
`Max Queue Size`	The MQTT messages are always being sent to subscribers on a topic. If the 'Run Schedule' is significantly behind the rate at which the messages are arriving to this processor then a back up can occur. This property specifies the maximum number of messages this processor will hold in memory at one time.**

```




## Requesting Access

This integration is only available with a [Qordoba Enterprise](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html) subscription.

If you are not a Qordoba Enterprise customer, you can inquire about our
Enterprise offering by [contacting us](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html).



