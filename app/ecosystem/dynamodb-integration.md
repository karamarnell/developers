---
id: page-plugin
title: Qordoba - Amazon DynamoDB integration
header_title: Qordoba - Amazon DynamoDB integration
header_icon: /assets/images/icons/plugins/dynamodb-integration.png
breadcrumbs:
  Plugins: /plugins
---

Qordoba's Amazon DynamoDB connector retrieves JSON documents from DynamoDB, including all attributes and content. It reads documents based on hash and range keys, which can be strings or numbers. For any GET request, all the primary keys are required (hash or hash and range based on the table keys).

```
You can host the DynamoDB connector in your environment or allow Qordoba to remotely access your databases.
```
You can customize your DynamoDB configuration using these parameters:

**Table Name** DynamoDB table name
**Hash Key Name** Hash key name of item
**Range Key Name** Range key name of item
**Hash Key Value** Hash key value of item (default `${dynamodb.item.hash.key.value}`)
**Range Key Value** Range key value of item (default `${dynamodb.item.range.key.value}`)
**Hash Key Value Type** Hash key value type of item
**JSON Document Attribute** JSON document to be retrieved from DynamoDB item
**Batch items for each request (1-50)** Items to be retrieved in one batch (default `1`)
**Access Key** Key provided for access to sensitive data
**Secret Key*** Key provided to encrypt and decrypt sensitive data
**Credentials File** Path to a file containing AWS access key and secret key in properties file format
**AWS Credentials Provider Service** Controller service used to obtain AWS credentials provider
**Communications Timeout** No Description Provided (Default `30 seconds`)
**SSL Context Service** Specifies an optional SSL context service which can be used to create connections

OLD:
Puts a document from DynamoDB based on hash and range key. The table can have either hash and range or hash key alone. Currently, the keys supported are strings and numbers, and the value can be a Json document. In case of hash and range keys, both key are required for the operation. The Qordoba content must be JSON. The Qordoba Content Editor is mapped to the specified Json Document attribute in the DynamoDB item.In the table below, you can view which parameters you can use to customize your configuration with this particular system:

NEW:
You can reintegrate JSON documents from Qordoba to DynamoDB. The connector will again read documents based on hash and range keys, which can be strings or numbers. In the case of hash and range keys, both keys are required for the operation. 

You can customize your configuration using the same parameter as above, plus:
**Character set of document** Specifies character set of document data (default `UTF-8`)
