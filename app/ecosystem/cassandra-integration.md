---
id: page-plugin
title: Qordoba - Cassandra integration
header_title:  Qordoba - Cassandra integration
header_icon: /assets/images/icons/plugins/cassandra-integration.png
breadcrumbs:
  Plugins: /plugins

---



<div class="alert alert-warning">
  Qordoba integration supports Cassandra1.x, 2.x, and 3.0.x cluster.
</div>

Qordoba can execute provided Cassandra Query Language (CQL) select query on a Cassandra. Query result can be converted to Avro or JSON format. Streaming is used, so arbitrarily large result sets are supported. This processor can be scheduled to run on a timer, using the standard scheduling methods, or can be triggered by an incoming Qordoba workflow. If it is triggered by an incoming Qordoba workflow, then attributes of that query will be available when evaluating the select query.



<div class="alert alert-warning">
Qordoba can send the data back by executing provided Cassandra Query Language (CQL) statement on a Cassandra 1.x, 2.x, or 3.0.x cluster. The content will be provided from Qordoba content editor.
</div>


In the table below, you can view which parameters you can use to customize your configuration with this particular system:

```javascript
'Cassandra Contact Points'	Contact points are addresses of Cassandra nodes. The list of contact points should be comma-separated and in hostname:port format. Example node1:port,node2:port,.... The default client port for Cassandra is 9042, but the port(s) must be explicitly specified.
'Keyspace'	The Cassandra Keyspace to connect to. If no keyspace is specified, the query will need to include the keyspace name before any table reference.
'SSL Context Service'	The SSL Context Service used to provide client certificate information for TLS/SSL connections.
'Client Auth'	Client authentication policy when connecting to secure (TLS/SSL) cluster. Possible values are REQUIRED, WANT, NONE. This property is only used when an SSL Context has been defined and enabled.
'Username'	Username to access the Cassandra cluster
'Password'	Password to access the Cassandra cluster Sensitive Property
'Consistency Level'	The strategy for how many replicas must respond before results are returned. #The default value ONE
'Character Set'		Specifies the character set of the record data. #The default value UTF-8
'CQL select query'	CQL select query Supports Expression Language 
'Max Wait Time'		The maximum amount of time allowed for a running CQL select query. Must be of format <duration> <TimeUnit> where <duration> is a non-negative integer and TimeUnit is a supported Time Unit, such as: nanos, millis, secs, mins, hrs, days. A value of zero means there is no limit. #The default value 0 seconds
'Fetch size'	The number of result rows to be fetched from the result set at a time. Zero is the default and means there is no limit. #The default value 0 
'Output Format'	The format to which the result rows will be converted. If JSON is selected, the output will contain an object with field 'results' containing an array of result rows. Each row in the array is a map of the named column to its value. For example: { "results": [{"userid":1, "name":"Joe Smith"}]}

```
---
## Requesting Access

This integration is only available with a [Qordoba Enterprise](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html) subscription.

If you are not a Qordoba Enterprise customer, you can inquire about our
Enterprise offering by [contacting us](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html).

