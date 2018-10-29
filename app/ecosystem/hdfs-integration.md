---
id: page-plugin
title: Qordoba - HDFS integration
header_title: Qordoba - HDFS integration
header_icon: /assets/images/icons/plugins/hdfs-integration.png
breadcrumbs:
  Plugins: /plugins
---

Qordoba provides a hosted connector to fetch and put file content from HDFS with an easy configuration. When you run the hosted Qordoba connector, you can add the below configs to get from and put data on HDFS.
In the tables below, you can view which parameters you can use to customize your configuration with this particular system:

Get data from HDFS

```javascript
'Additional Classpath Resources' A comma-separated list of paths to files and/or directories that will be added to the classpath. When specifying a directory, all files with in the directory will be added to the classpath, but further sub-directories will not be included.
'Compression codec'	No Description Provided. 
'Hadoop Configuration Resources'	A file or comma separated list of files which contains the Hadoop file system configuration. Without this, Hadoop will search the classpath for a 'core-site.xml' and 'hdfs-site.xml' file or will revert to a default configuration.
'HDFS Filename'	${path}/${filename}	The name of the HDFS file to retrieve
'Kerberos Keytab'	Kerberos keytab associated with the principal. Requires nifi.kerberos.krb5.file to be set in your nifi.properties
'Kerberos principal' to authenticate as. Requires nifi.kerberos.krb5.file to be set in your nifi.properties
'Kerberos Relogin Period'	Period of time which should pass before attempting a kerberos relogin #the default value is 4 hours
```

Put data on HDFS

```javascript
'Hadoop Configuration Resources'	A file or comma separated list of files which contains the Hadoop file system configuration. Without this, Hadoop will search the classpath for a 'core-site.xml' and 'hdfs-site.xml' file or will revert to a default configuration.
'Kerberos Principal'	Kerberos principal to authenticate as. Requires nifi.kerberos.krb5.file to be set in your nifi.properties
'Kerberos Keytab'	Kerberos keytab associated with the principal. Requires nifi.kerberos.krb5.file to be set in your nifi.properties
'Kerberos Relogin Period'	Period of time which should pass before attempting a kerberos relogin #the default value is 4 hours
'Additional Classpath Resources' A comma-separated list of paths to files and/or directories that will be added to the classpath. When specifying a directory, all files with in the directory will be added to the classpath, but further sub-directories will not be included.
'Directory'	The parent HDFS directory to which files should be written
'Conflict Resolution Strategy' Indicates what should happen when a file with the same name already exists in the output directory #the default value is fail
'Block Size'	Size of each block as written to HDFS. This overrides the Hadoop Configuration
'IO Buffer Size'	Amount of memory to use to buffer file contents during IO. This overrides the Hadoop Configuration
'Replication'	Number of times that HDFS will replicate each file. This overrides the Hadoop Configuration
'Permissions unmask'	A umask represented as an octal number which determines the permissions of files written to HDFS. This overrides the Hadoop Configuration dfs.umaskmode
'Remote Owner'	Changes the owner of the HDFS file to this value after it is written. This only works if NiFi is running as a user that has HDFS super user privilege to change owner
'Remote Group'	Changes the group of the HDFS file to this value after it is written. This only works if NiFi is running as a user that has HDFS super user privilege to change group
'Compression codec'	No Description Provided. #the default value is NONE
```


---
## Requesting Access

This integration is only available with a [Qordoba Enterprise](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html) subscription.

If you are not a Qordoba Enterprise customer, you can inquire about our
Enterprise offering by [contacting us](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html).

