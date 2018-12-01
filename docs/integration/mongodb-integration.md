---
id: page-plugin
title: Qordoba - MongoDB integration
header_title: Qordoba - MongoDB integration
header_icon: /assets/images/icons/plugins/mongodb-integration.png
breadcrumbs:
  Plugins: /plugins
---

```
We recommend using the hosted version.
```

Qordoba can play nicely with MongoDB - you can translate all you content with just a config update!
In the tables below, you can view which parameters you can use to customize your configuration with this particular system:

```
`Mongo URI`	MongoURI, typically of the form: mongodb://host1[:port1][,host2[:port2],...]
`Mongo Database Name`	The name of the database to use
`Mongo Collection Name`	The name of the collection to use
`SSL Context Service`	The SSL Context Service used to provide client certificate information for TLS/SSL connections.
`Client Auth`	REQUIRED	Client authentication policy when connecting to secure (TLS/SSL) cluster. Possible values are REQUIRED, WANT, NONE. This property is only used when an SSL Context has been defined and enabled.
`Query`	The selection criteria; must be a valid MongoDB Extended JSON format; if omitted the entire collection will be queried
`Projection`	The fields to be returned from the documents in the result set; must be a valid BSON document
`Sort`	The fields by which to sort; must be a valid BSON document
`Limit`	The maximum number of elements to return
`Batch Size`	The number of elements returned from the server in one batch
`SSL Context Service` The SSL Context Service used to provide client certificate information for TLS/SSL connections.
`Client Auth`	REQUIRED	Client authentication policy when connecting to secure (TLS/SSL) cluster. Possible values are REQUIRED, WANT, NONE. This property is only used when an SSL Context has been defined and enabled.
```

```
`Mongo URI`	MongoURI, typically of the form: mongodb://host1[:port1][,host2[:port2],...]
`Mongo Database Name`	The name of the database to use
`Mongo Collection Name`	The name of the collection to use
`SSL Context Service`	The SSL Context Service used to provide client certificate information for TLS/SSL connections.
`Client Auth`	REQUIRED	Client authentication policy when connecting to secure (TLS/SSL) cluster. Possible values are REQUIRED, WANT, NONE. This property is only used when an SSL Context has been defined and enabled.
`Mode`	insert	Indicates whether the processor should insert or update content
`Upsert`	false	When true, inserts a document if no document matches the update query criteria; this property is valid only when using update mode, otherwise it is ignored
`Update Query Key`	_id	Key name used to build the update query criteria; this property is valid only when using update mode, otherwise it is ignored
`Write Concern`	ACKNOWLEDGED	The write concern to use
`Character Set`	UTF-8	The Character Set in which the data is encoded
```
