---
id: page-plugin
title: Qordoba - IMAP integration
header_title: Qordoba - IMAP integration
header_icon: /assets/images/icons/plugins/imap-integration.png
breadcrumbs:
  Plugins: /plugins
---

The Qordoba platform can consume messages from email servers using the IMAP protocol. The raw-bytes of each received email message are written as content. You can send or forward the email directly to your dedicated IPs.
In the table below, you can view which parameters you can use to customize your configuration with this particular system:

```java
'Host Name'	Network address of Email server (e.g., pop.gmail.com, imap.gmail.com . . .)
'Port' Numeric value identifying Port of Email server (e.g., 993)
'User Name'	User Name used for authentication and authorization with Email server.
'Password'	Password used for authentication and authorization with Email server.
'Folder'	Email folder to retrieve messages from (e.g., INBOX) #the default value is INBOX
'Fetch Size' Specify the maximum number of Messages to fetch per call to Email Server. #the default value is 10
'Delete Messages'	Specify whether mail messages should be deleted after retrieval. #the default value is false
'Connection Timeout'	The amount of time to wait to connect to Email server #the default value is 30 seconds
'Mark Messages as Read'	Specify if messages should be marked as read after retrieval. #the default value is false
'Use SSL'	Specifies if IMAP connection must be obtained via SSL encrypted connection (i.e., IMAPS) #the default value is true
```
