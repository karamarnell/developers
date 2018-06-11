---
id: page-plugin
title: Qordoba - Elasticsearch integration
header_title: Qordoba - Elasticsearch integration
header_icon: /assets/images/icons/plugins/elasticsearch-elastic-integration.png
breadcrumbs:
  Plugins: /plugins
---
Qordoba can retrieve documents from Elasticsearch using your specified connection properties and the identifier of the documents. Qordoba can make secure connections if the cluster is configured for authorization and/or secure transport (SSL/TLS) and the Shield plugin is available.

<div class="alert alert-warning">
This integration supports Elasticsearch 2.x clusters and Elasticsearch 5.x clusters.
</div>

If you approve the DynamoDB wording, I'd be consistent and repeat it here to introduce this list of parameters, so this would read: 

You can customize your Elasticsearch configuration using these parameters: 

**Cluster Name** Name of Elasticsearch cluster. *For example: elasticsearch_brew.* (default `elasticsearch`)

**Elasticsearch Hosts** Elasticsearch Hosts, which should be written with colons and separated by commas for hostname/port host1:port,host2:port,.... *For example, testcluster:9300. This processor uses the Transport Client to connect to hosts. The default transport client port is 9300.*

**SSL Context Service** The SSL Context Service used to provide client certificate information for TLS/SSL connections. This service only applies if the Elasticsearch endpoint(s) have been secured with TLS/SSL.

**Shield Plugin Filename** Specifies the path to the JAR for the Elasticsearch Shield plugin. If the Elasticsearch cluster has been secured with the Shield plugin, then the Shield plugin JAR must also be available to this processor. 

**Username** Username to access the Elasticsearch cluster

**Password** Password to access the Elasticsearch cluster, including sensitive information

**ElasticSearch Ping Timeout ** Ping timeout used to determine when a node is unreachable. If non-local, recommended timeout is 30 seconds, or 30s (default `5s`)
**Sampler Interval** How often to sample/ping the nodes. For example, 5s (5 seconds). If non-local, recommended sampler is 30 seconds, or 30s (default `5s`)

**Document Identifier** Identifier for document to be fetched

**Index** Name of index to read from

**Type** Type of document used by Elasticsearch for indexing and searching

**Character set of document** Specifies character set of document data (default `UTF-8`)

NOTE: I edited copy above. Original table is below, without any copy edits, for your reference.

```java
'Cluster Name'	Name of the Elasticsearch cluster (for example, elasticsearch_brew). And the defaults value is elasticsearch.
'ElasticSearch Hosts'	ElasticSearch Hosts, which should be comma separated and colon for hostname/port host1:port,host2:port,.... For example testcluster:9300. This processor uses the Transport Client to connect to hosts. The default transport client port is 9300.
'SSL Context Service'	The SSL Context Service used to provide client certificate information for TLS/SSL connections. This service only applies if the Elasticsearch endpoint(s) have been secured with TLS/SSL.
'Shield Plugin Filename'	Specifies the path to the JAR for the Elasticsearch Shield plugin. If the Elasticsearch cluster has been secured with the Shield plugin, then the Shield plugin JAR must also be available to this processor. 
'Username'	Username to access the Elasticsearch cluster
'Password'	Password to access the Elasticsearch cluster Sensitive Property 
'ElasticSearch Ping Timeout' the default is 5s	The ping timeout used to determine when a node is unreachable. For example, 5s (5 seconds). If non-local recommended is 30s
'Sampler Interval'the default is How often to sample / ping the nodes listed and connected. For example, 5s (5 seconds). If non-local recommended is 30s.
'Document Identifier' The identifier for the document to be fetched Supports Expression Language
'Index'	The name of the index to read from
'Type'	The type of this document used by Elasticsearch for indexing and searching
'Character Set'	UTF-8	Specifies the character set of the document data.
```


---
## Requesting Access

This integration is only available with a [Qordoba Enterprise](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html) subscription.

If you are not a Qordoba Enterprise customer, you can inquire about our
Enterprise offering by [contacting us](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html).
