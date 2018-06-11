---
id: page-plugin
title: Qordoba - SMTP integration
header_title: Qordoba - SMTP integration
header_icon: /assets/images/icons/plugins/smtp-integration.png
breadcrumbs:
  Plugins: /plugins
---



Qordoba implements a lightweight SMTP server to an arbitrary port, allowing Qordoba to listen for incoming email. Note this server does not perform any email validation. If direct exposure to the internet is sought. 


<div class="alert alert-warning">
When you use this project Qordoba will assign unique host & IP per customer account
</div>

```java

`Listening Port`			The TCP port the ListenSMTP processor will bind to.NOTE that on Unix derivative operating systems this port must be higher than 1024 unless NiFi is running as with root user permissions.
`Maximum number of SMTP connection`	1		The maximum number of simultaneous SMTP connections.
`SMTP connection timeout`	60 seconds		The maximum time to wait for an action of SMTP client.
`SMTP Maximum Message Size`	20 MB		The maximum number of bytes the server will accept.
`SSL Context Service`	The Controller Service to use in order to obtain an SSL Context. If this property is set, messages will be received over a secure connection.
`Client Auth`	NONE REQUIRED The client authentication policy to use for the SSL Context. Only used if an SSL Context Service is provided.
`SMTP hostname`		The hostname to be embedded into the banner displayed when an SMTP client connects to the processor TCP port .

```

---
## Requesting Access

This integration is only available with a [Qordoba Enterprise](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html) subscription.

If you are not a Qordoba Enterprise customer, you can inquire about our
Enterprise offering by [contacting us](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html).
