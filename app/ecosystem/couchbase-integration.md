---
id: page-plugin
title: Qordoba - Couchbase integration
header_title:  Qordoba - Couchbase integration
header_icon: /assets/images/icons/plugins/couchbase-integration.png
breadcrumbs:
  Plugins: /plugins
---

The Qordoba connector can pull and push data to Couchbase Server directly and in an automated way.

You can get a document from the Couchbase Server via Key/Value access. The ID of the document to fetch may be supplied by setting the <Document Id> property.

In the table below, you can view which parameters you can use to customize your configuration with this particular system:

```
'Couchbase Cluster Controller Service'	A Couchbase Cluster Controller Service which manages connections to a Couchbase cluster.
'Bucket Name' The name of bucket to access.
'Document Type'	The Json type of contents.
'Document ID'	A static, fixed Couchbase document id, or an expression to construct the Couchbase document id.

```
Push a document to Couchbase Server via Key/Value access.

```
'Couchbase Cluster Controller Service'	A Couchbase Cluster Controller Service which manages connections to a Couchbase cluster.
'Bucket Name' The name of bucket to access.
'Document Type'	The Json type of contents.
'Document ID'	A static, fixed Couchbase document id, or an expression to construct the Couchbase document id.
'Persist To'	Durability constraint about disk persistence. #the default is NONE
'Replicate To'	Durability constraint about replication. #the default is NONE
```

```
NOTE: if the Document ID property is not set, the contents will be read to determine the Document ID. This means that the contents of the entire WHAT will be buffered in memory (if you are using the hosted connector)
```
