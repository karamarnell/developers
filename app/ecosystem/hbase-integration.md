---
id: page-plugin
title: Qordoba - HBase integration
header_title: Qordoba - HBase integration
header_icon: /assets/images/icons/plugins/hbase-integration.png
breadcrumbs:
  Plugins: /plugins
---

Qordoba provides a hosted connector to get and put content on HBase with an easy configuration. When you run the Docker image with Qordoba connector, you can add the below config.

In the tables below, you can view which parameters you can use to customize your configuration with this particular system:


Get data from HBase

```javascript
'HBase Client Service' Specifies the Controller Service to use for accessing HBase.
'Distributed Cache Service' Specifies the Controller Service that should be used to maintain state about what has been pulled from HBase so that if a new node begins pulling data, it won't duplicate all of the work that has been done.
'Table Name'The name of the HBase Table to put data into
'Columns' A comma-separated list of "<colFamily>:<colQualifier>" pairs to return when scanning. To return all columns for a given family, leave off the qualifier such as "<colFamily1>,<colFamily2>".
'Filter Expression'	An HBase filter expression that will be applied to the scan. This property can not be used when also using the Columns property.
'Initial Time Range'	None	The time range to use on the first scan of a table. None will pull the entire table on the first scan, Current Time will pull entries from that point forward.
'Character Set'	UTF-8	Specifies which character set is used to encode the data in HBase
```

Put data on HBase as JSON

```javascript
'HBase Client Service'	Specifies the Controller Service to use for accessing HBase.
'Table Name' The name of the HBase Table to put data into
'Row Identifier'	
Specifies the Row ID to use when inserting data into HBase
'Row Identifier Field Name'	Specifies the name of a JSON element whose value should be used as the row id for the given JSON document.
'Row Identifier Encoding Strategy'	Specifies the data type of Row ID used when inserting data into HBase. The default behavior is to convert the row id to a UTF-8 byte array. Choosing Binary will convert a binary formatted string to the correct byte[] representation. The Binary option should be used if you are using Binary row keys in HBase
'Column Family'	String	The Column Family to use when inserting data into HBase
'Batch Size'	25	The maximum number of FlowFiles to process in a single execution. The FlowFiles will be grouped by table, and a single Put per table will be performed.
'Complex Field Strategy	'Text	Indicates how to handle complex fields, i.e. fields that do not have a single text value.
'Field Encoding Strategy'	String	Indicates how to store the value of each field in HBase. The default behavior is to convert each value from the JSON to a String, and store the UTF-8 bytes. Choosing Bytes will interpret the type of each field from the JSON, and convert the value to the byte representation of that type, meaning an integer will be stored as the byte representation of that integer.

```


---
## Requesting Access

This integration is only available with a [Qordoba Enterprise](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html) subscription.

If you are not a Qordoba Enterprise customer, you can inquire about our
Enterprise offering by [contacting us](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html).

