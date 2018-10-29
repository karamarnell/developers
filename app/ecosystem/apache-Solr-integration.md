---
id: page-plugin
title: Qordoba - Solr integration
header_title: Qordoba - Solr integration
header_icon: /assets/images/icons/plugins/apache-solr-integration.png
breadcrumbs:
  Plugins: /plugins
---


Qordoba can retrieve a document from Solr using the specified connection properties and the identifier of the document to retrieve. 
In the table below, you can view which parameters you can use to customize your configuration with this particular system:


####Read from Solr index
```javascript
`Solr Type`	Standard or Cloud A SolrCloud instance. Standard A stand-alone Solr instance.The type of Solr instance, Cloud or Standard.
`Solr Location`			The Solr url for a Solr Type of Standard (ex: http://localhost:8984/solr/gettingstarted), or the ZooKeeper hosts for a Solr Type of Cloud (ex: localhost:9983).
`Collection`			The Solr collection name, only used with a Solr Type of Cloud
`Solr Query`			A query to execute against Solr
`Return Fields`			Comma-separated list of fields names to return
`Sort Clause`			A Solr sort clause, ex: field1 asc, field2 desc
`Date Field`			The name of a date field in Solr used to filter results
`Batch Size`	100		Number of rows per Solr query
`JAAS Client App Name`			The name of the JAAS configuration entry to use when performing Kerberos authentication to Solr. If this property is not provided, Kerberos authentication will not be attempted. The value must match an entry in the file specified by the system property java.security.auth.login.config.
`SSL Context Service`	The Controller Service to use in order to obtain an SSL Context. This property must be set when communicating with a Solr over https.
`Solr Socket Timeout`	10 seconds	The amount of time to wait for data on a socket connection to Solr. A value of 0 indicates an infinite timeout.
Solr Connection Timeout	10 seconds		The amount of time to wait when establishing a connection to Solr. A value of 0 indicates an infinite timeout.
`Solr Maximum Connections`	10		The maximum number of total connections allowed from the Solr client to Solr.
`Solr Maximum Connections Per Host`	5		The maximum number of connections allowed from the Solr client to a single Solr host.
`ZooKeeper Client Timeout`	10 seconds		The amount of time to wait for data on a connection to ZooKeeper, only used with a Solr Type of Cloud.
`ZooKeeper Connection Timeout`	10 seconds		The amount of time to wait when establishing a connection to ZooKeeper, only used with a Solr Type of Cloud.
```

####Sends the content as a ContentStream to Solr

```javascript
`Solr Type`	Standard or Cloud A SolrCloud instance. Standard A stand-alone Solr instance. The type of Solr instance, Cloud or Standard.
`Solr Location`			The Solr url for a Solr Type of Standard (ex: http://localhost:8984/solr/gettingstarted), or the ZooKeeper hosts for a Solr Type of Cloud (ex: localhost:9983).
`Collection`			The Solr collection name, only used with a Solr Type of Cloud
`Content Stream Path`	/update/json/docs		The path in Solr to post the ContentStream
`Content-Type`	application/json		Content-Type being sent to Solr
`Commit Within`	5000	The number of milliseconds before the given update is committed
`JAAS Client App Name`	The name of the JAAS configuration entry to use when performing Kerberos authentication to Solr. If this property is not provided, Kerberos authentication will not be attempted. The value must match an entry in the file specified by the system property java.security.auth.login.config.
`SSL Context Service`	The Controller Service to use in order to obtain an SSL Context. This property must be set when communicating with a Solr over https.
`Solr Socket Timeout`	10 seconds		The amount of time to wait for data on a socket connection to Solr. A value of 0 indicates an infinite timeout.
`Solr Connection Timeout`	10 seconds	The amount of time to wait when establishing a connection to Solr. A value of 0 indicates an infinite timeout.
`Solr Maximum Connections`	10		The maximum number of total connections allowed from the Solr client to Solr.
`Solr Maximum Connections Per Host`	5	The maximum number of connections allowed from the Solr client to a single Solr host.
`ZooKeeper Client Timeout`	10 seconds	The amount of time to wait for data on a connection to ZooKeeper, only used with a Solr Type of Cloud.
`ZooKeeper Connection Timeout`	10 seconds	The amount of time to wait when establishing a connection to ZooKeeper, only used with a Solr Type of Cloud.

```
---
## Requesting Access

This integration is only available with a [Qordoba Enterprise](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html) subscription.

If you are not a Qordoba Enterprise customer, you can inquire about our
Enterprise offering by [contacting us](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html).
