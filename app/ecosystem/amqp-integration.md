---
id: page-plugin
title: Qordoba - AMQP integration
header_title: Qordoba - AMQP integration
header_icon: /assets/images/icons/plugins/amqp-integration.png
breadcrumbs:
  Plugins: /plugins
---


Qordoba provides a typical AMQP exchange integration in two ways, the message that is sent to the AMQP Exchange will be routed based on the 'Routing Key' to its final destination in the l10n workflow (the binding). 


<div class="alert alert-warning">
AMQP Version. Currently only supports AMQP v0.9.1.
</div>

In the tables below, you can view which parameters you can use to customize your configuration with this particular system:


####Consumes AMQP Message configuration
```javascript
'Queue'	The name of the existing AMQP Queue from which messages will be consumed. Usually pre-defined by AMQP administrator.
'Host Name'	Network address of AMQP broker #The default value localhost
'Port'		Numeric value identifying Port of AMQP broker #The default value 5672
'Virtual Host'	Virtual Host name which segregates AMQP system for enhanced security.
'User Name'		User Name used for authentication and authorization. #The default value guest
'Password'		Password used for authentication and authorization Sensitive Property #The default value guest
'SSL Context Service'	The SSL Context Service used to provide client certificate information for TLS/SSL connections.
'Client Auth'	Client authentication policy when connecting to secure (TLS/SSL) AMQP broker. Possible values are REQUIRED, WANT, NONE. This property is only used when an SSL Context has been defined and enabled.

```


####Publish content AMQP Message configuration
```javascript

'Exchange Name'	The name of the AMQP Exchange the messages will be sent to. Usually provided by the AMQP administrator. It is an optional property. If kept empty the messages will be sent to a default AMQP exchange.
'Routing Key' The name of the Routing Key that will be used by AMQP to route messages from the exchange to a destination queue(s). Usually provided by the administrator in the event when messages are sent to a default exchange this property corresponds to a destination queue name, otherwise a binding from the Exchange to a Queue via Routing Key must be set (usually by the AMQP administrator)
'Host Name'	Network address of AMQP broker #The default value localhost
'Port'		Numeric value identifying Port of AMQP broker #The default value guest 5672 
'Virtual Host'	Virtual Host name which segregates AMQP system for enhanced security.
'User Name'	User Name used for authentication and authorization. 
'Password'	Password used for authentication and authorization Sensitive Property #The default value guest
'SSL Context Service'	The SSL Context Service used to provide client certificate information for TLS/SSL connections.
'Client Auth'	Client authentication policy when connecting to secure (TLS/SSL) AMQP broker. Possible values are REQUIRED, WANT, NONE. This property is only used when an SSL Context has been defined and enabled.

```

---
## Requesting Access

This integration is only available with a [Qordoba Enterprise](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html) subscription.

If you are not a Qordoba Enterprise customer, you can inquire about our
Enterprise offering by [contacting us](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html).



