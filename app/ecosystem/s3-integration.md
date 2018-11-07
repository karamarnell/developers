---
id: page-plugin
title: Qordoba - Amazon S3 integration
header_title: Qordoba - Amazon S3 integration
header_icon: /assets/images/icons/plugins/s3-integration.png
breadcrumbs:
  Plugins: /plugins
---

Qordoba can sync S3 buckets. For each object that is listed, Qordoba creates a FlowFile that represents the object so that it can be fetched in conjunction with the FetchS3Object. This processor is designed to run on Primary Node only in a cluster. If the primary node changes, the new primary node will pick up where the previous node left off without duplicating all of the data.
In the table below, you can view which parameters you can use to customize your configuration with this particular system:

```
`Bucket`	No Description Provided.
`Object Key`	${filename}	No Description Provided.
`Region`	us-west-2	No Description Provided.
`Access Key`	No Description Provided.Sensitive Property: true
`Secret Key`	No Description Provided.Sensitive Property: true
`Credentials File`	Path to a file containing AWS access key and secret key in properties file format.
`AWS Credentials Provider Service`	The Controller Service that is used to obtain aws credentials provider
`Communications Timeout`	30 secs	No Description Provided.
`Version`	The Version of the Object to download
`SSL Context Service`	Specifies an optional SSL Context Service that, if provided, will be used to create connections
`Endpoint Override URL`	Endpoint URL to use instead of the AWS default including scheme, host, port, and path. The AWS libraries select an endpoint URL based on the AWS region, but this property overrides the selected endpoint URL, allowing use with other S3-compatible endpoints.
`Signer Override`	The AWS libraries use the default signer but this property allows you to specify a custom signer to support older S3-compatible services.
`Proxy Host`	Proxy host name or IP
`Proxy Host Port`	Proxy host port
```

```
`Object Key`	${filename}	No Description Provided.
`Bucket`	No Description Provided.
`Content Type`	Sets the Content-Type HTTP header indicating the type of content stored in the associated object. The value of this header is a standard MIME type. AWS S3 Java client will attempt to determine the correct content type if one hasn't been set yet. Users are responsible for ensuring a suitable content type is set when uploading streams. If no content type is provided and cannot be determined by the filename, the default content type "application/octet-stream" will be used.
`Access Key`	No Description Provided. Sensitive Property: true
`Secret Key`	No Description Provided. Sensitive Property: true
`Credentials File`	Path to a file containing AWS access key and secret key in properties file format.
`AWS Credentials Provider service`	The Controller Service that is used to obtain aws credentials provider
`Storage Class`	Standard	No Description Provided.
`Region`	us-west-2	No Description Provided.
`Communications Timeout`	30 secs	No Description Provided.
`Expiration Time Rule`	No Description Provided.
`FullControl User List`	${s3.permissions.full.users}	A comma-separated list of Amazon User ID's or E-mail addresses that specifies who should have Full Control for an object
`Read Permission User List`	${s3.permissions.read.users}	A comma-separated list of Amazon User ID's or E-mail addresses that specifies who should have Read Access for an object
`Write Permission User List`	${s3.permissions.write.users}	A comma-separated list of Amazon User ID's or E-mail addresses that specifies who should have Write Access for an object
`Read ACL User List`	${s3.permissions.readacl.users}	A comma-separated list of Amazon User ID's or E-mail addresses that specifies who should have permissions to read the Access Control List for an object
Supports Expression Language: true
`Write ACL User List`	${s3.permissions.writeacl.users}	A comma-separated list of Amazon User ID's or E-mail addresses that specifies who should have permissions to change the Access Control List for an object
Supports Expression Language: true
`Owner`	${s3.owner}	The Amazon ID to use for the object's owner
`Canned ACL`	${s3.permissions.cannedacl}	Amazon Canned ACL for an object, one of: BucketOwnerFullControl, BucketOwnerRead, LogDeliveryWrite, AuthenticatedRead, PublicReadWrite, PublicRead, Private; will be ignored if any other ACL/permission/owner property is specified
`SSL Context Service`	
Specifies an optional SSL Context Service that, if provided, will be used to create connections
`Endpoint Override URL`	Endpoint URL to use instead of the AWS default including scheme, host, port, and path. The AWS libraries select an endpoint URL based on the AWS region, but this property overrides the selected endpoint URL, allowing use with other S3-compatible endpoints.
`Signer Override`	Default Signature	The AWS libraries use the default signer but this property allows you to specify a custom signer to support older S3-compatible services.
`Multipart Threshold`	5 GB	Specifies the file size threshold for switch from the PutS3Object API to the PutS3MultipartUpload API. Flow files bigger than this limit will be sent using the stateful multipart process. The valid range is 50MB to 5GB.
`Multipart Part Size`	5 GB	Specifies the part size for use when the PutS3Multipart Upload API is used. Flow files will be broken into chunks of this size for the upload process, but the last part sent can be smaller since it is not padded. The valid range is 50MB to 5GB.
`Multipart Upload AgeOff Interval`	60 min	Specifies the interval at which existing multipart uploads in AWS S3 will be evaluated for ageoff. When processor is triggered it will initiate the ageoff evaluation if this interval has been exceeded.
`Multipart Upload Max Age Threshold`	7 days	Specifies the maximum age for existing multipart uploads in AWS S3. When the ageoff process occurs, any upload older than this threshold will be aborted. Server Side Encryption	None Specifies the algorithm used for server side encryption.
`Proxy Host`	Proxy host name or IP
`Proxy Host Port`	Proxy host port
```
