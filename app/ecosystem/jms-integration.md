---
id: page-plugin
title: Qordoba - Java Message Service integration
header_title: Qordoba - Java Message Service integration
header_icon: /assets/images/icons/plugins/jms-integration.png
breadcrumbs:
  Plugins: /plugins
nav:
  - label: Getting Started
    items:
      - label: Configuration
  - label: Documentation
    items:
      - label: How it works
      - label: Generators
      - label: FAQ
---

The Qordoba platform can receive or pull JMS message content, and after l10n, this content can be sent back and published to the same or different topics.

In the tables below, you can view which parameters you can use to customize your configuration with this particular system:

```
'Connection Factory Service'	The Controller Service that is used to obtain ConnectionFactory
'Destination Name'	The name of the JMS Destination. Usually provided by the administrator (e.g., 'topic://myTopic' or 'myTopic').
'Destination Type'	The type of the JMS Destination. Could be one of 'QUEUE' or 'TOPIC'. Usually provided by the administrator. Defaults to 'TOPIC
'User Name'	User Name used for authentication and authorization.
'Password'	Password used for authentication and authorization.
'Session Cache Size' The maximum limit for the number of cached Sessions. #the default value is 1
'Acknowledgment Mode'	The JMS Acknowledgement Mode. Using Auto Acknowledge can cause messages to be lost on restart of NiFi but may provide better performance than Client Acknowledge. #the default value is 2
```

```
'JMS Provider'The Provider used for the JMS Server #the default value is ActiveMQ
'URL'	The URL of the JMS Server
'Destination Name'	The name of the JMS Topic or queue to use
'Communications Timeout'	The amount of time to wait when attempting to receive a message before giving up and assuming failure #the default value is 30 seconds
'Message Batch Size'	The number of messages to pull/push in a single iteration of the processor #the default value is 10
'Username'	Username used for authentication and authorization
'Password'	Password used for authentication and authorization
'SSL Context Service'	The Controller Service to use in order to obtain an SSL Context.
'Acknowledgment Mode'	The JMS Acknowledgement Mode. Using Auto Acknowledge can cause messages to be lost on restart of NiFi but may provide better performance than Client Acknowledge. #the default value is Client Acknowledge
'Message Selector'	The JMS Message Selector to use in order to narrow the messages that are pulled
'Copy JMS Properties to Attributes'	Whether or not the JMS Message Properties should be copied to the FlowFile Attributes; if so, the attribute name will be jms.XXX, where XXX is the JMS Property name #the default value is true
'Client ID Prefix'	A human-readable ID that can be used to associate connections with yourself so that the maintainers of the JMS Server know who to contact if problems arise
'Use Durable Subscription'	If true, connections to the specified topic will use Durable Subscription so that messages are queued when we are not pulling them #the default value is false
```

```
'Connection Factory Service'	The Controller Service that is used to obtain ConnectionFactory
'Destination Name'	The name of the JMS Destination. Usually provided by the administrator (e.g., 'topic://myTopic' or 'myTopic').
'Destination Type' The type of the JMS Destination. Could be one of 'QUEUE' or 'TOPIC'. Usually provided by the administrator. Defaults to 'TOPIC' #the default value is QUEUE
'User Name'	User Name used for authentication and authorization.
'Password'	Password used for authentication and authorization.
'Session Cache Size'	The maximum limit for the number of cached Sessions.
```
