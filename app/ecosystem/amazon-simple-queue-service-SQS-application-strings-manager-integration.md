---
id: page-plugin
title: Qordoba - Amazon simple queue service SQS i18n integration
header_title: Qordoba - Amazon simple queue service SQS integration
header_icon: /assets/images/icons/plugins/amazon-simple-queue-service-SQS-i18n-integration.png
breadcrumbs:
  Plugins: /plugins
---

Qordoba's Amazon SQS i18n Integration retrieves the content from message based on key. 

```json
[
  {
    "Name": "Queue URL",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The URL of the queue to act upon\nSupports Expression Language: true"
  },
  {
    "Name": "Auto Delete Messages",
    "Default Value": "true",
    "Allowable Values": "true\nfalse",
    "Description": "Specifies whether the messages should be automatically deleted by the processors once they have been received."
  },
  {
    "Name": "Access Key",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "No Description Provided.\nSensitive Property: true\nSupports Expression Language: true"
  },
  {
    "Name": "Secret Key",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "No Description Provided.\nSensitive Property: true\nSupports Expression Language: true"
  },
  {
    "Name": "Credentials File",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "Path to a file containing AWS access key and secret key in properties file format."
  },
  {
    "Name": "AWS Credentials Provider service",
    "Default Value": "",
    "Allowable Values": "Controller Service API: \nAWSCredentialsProviderService\nImplementation:\nAWSCredentialsProviderControllerService",
    "Description": "The Controller Service that is used to obtain aws credentials provider"
  },
  {
    "Name": "Region",
    "Default Value": "us-west-2",
    "Allowable Values": "us-gov-west-1 \nus-east-1 \nus-west-1 \nus-west-2 \neu-west-1 \neu-central-1 \nap-southeast-1 \nap-southeast-2 \nap-northeast-1 \nap-northeast-2 \nsa-east-1 \ncn-north-1",
    "Description": "No Description Provided."
  },
  {
    "Name": "Batch Size",
    "Default Value": 10,
    "Allowable Values": "",
    "Description": "The maximum number of messages to send in a single network request"
  },
  {
    "Name": "Communications Timeout",
    "Default Value": "30 secs",
    "Allowable Values": "",
    "Description": "No Description Provided."
  },
  {
    "Name": "Character Set",
    "Default Value": "UTF-8",
    "Allowable Values": "Big5\nBig5-HKSCS\nCESU-8\nEUC-JP\nEUC-KR\nGB18030\nGB2312\nGBK\nIBM-Thai\nIBM00858\nIBM01140\nIBM01141\nIBM01142\nIBM01143\nIBM01144\nIBM01145\nIBM01146\nIBM01147\nIBM01148\nIBM01149\nIBM037\nIBM1026\nIBM1047\nIBM273\nIBM277\nIBM278\nIBM280\nIBM284\nIBM285\nIBM290\nIBM297\nIBM420\nIBM424\nIBM437\nIBM500\nIBM775\nIBM850\nIBM852\nIBM855\nIBM857\nIBM860\nIBM861\nIBM862\nIBM863\nIBM864\nIBM865\nIBM866\nIBM868\nIBM869\nIBM870\nIBM871\nIBM918\nISO-2022-CN\nISO-2022-JP\nISO-2022-JP-2\nISO-2022-KR\nISO-8859-1\nISO-8859-13\nISO-8859-15\nISO-8859-2\nISO-8859-3\nISO-8859-4\nISO-8859-5\nISO-8859-6\nISO-8859-7\nISO-8859-8\nISO-8859-9\nJIS_X0201\nJIS_X0212-1990\nKOI8-R\nKOI8-U\nShift_JIS\nTIS-620\nUS-ASCII\nUTF-16\nUTF-16BE\nUTF-16LE\nUTF-32\nUTF-32BE\nUTF-32LE\nUTF-8\nwindows-1250\nwindows-1251\nwindows-1252\nwindows-1253\nwindows-1254\nwindows-1255\nwindows-1256\nwindows-1257\nwindows-1258\nwindows-31j\nx-Big5-HKSCS-2001\nx-Big5-Solaris\nx-COMPOUND_TEXT\nx-euc-jp-linux\nx-EUC-TW\nx-eucJP-Open\nx-IBM1006\nx-IBM1025\nx-IBM1046\nx-IBM1097\nx-IBM1098\nx-IBM1112\nx-IBM1122\nx-IBM1123\nx-IBM1124\nx-IBM1166\nx-IBM1364\nx-IBM1381\nx-IBM1383\nx-IBM300\nx-IBM33722\nx-IBM737\nx-IBM833\nx-IBM834\nx-IBM856\nx-IBM874\nx-IBM875\nx-IBM921\nx-IBM922\nx-IBM930\nx-IBM933\nx-IBM935\nx-IBM937\nx-IBM939\nx-IBM942\nx-IBM942C\nx-IBM943\nx-IBM943C\nx-IBM948\nx-IBM949\nx-IBM949C\nx-IBM950\nx-IBM964\nx-IBM970\nx-ISCII91\nx-ISO-2022-CN-CNS\nx-ISO-2022-CN-GB\nx-iso-8859-11\nx-JIS0208\nx-JISAutoDetect\nx-Johab\nx-MacArabic\nx-MacCentralEurope\nx-MacCroatian\nx-MacCyrillic\nx-MacDingbat\nx-MacGreek\nx-MacHebrew\nx-MacIceland\nx-MacRoman\nx-MacRomania\nx-MacSymbol\nx-MacThai\nx-MacTurkish\nx-MacUkraine\nx-MS932_0213\nx-MS950-HKSCS\nx-MS950-HKSCS-XP\nx-mswin-936\nx-PCK\nx-SJIS_0213\nx-UTF-16LE-BOM\nX-UTF-32BE-BOM\nX-UTF-32LE-BOM\nx-windows-50220\nx-windows-50221\nx-windows-874\nx-windows-949\nx-windows-950\nx-windows-iso2022jp",
    "Description": "The Character Set that should be used to encode the textual content of the SQS message"
  },
  {
    "Name": "Visibility Timeout",
    "Default Value": "15 mins",
    "Allowable Values": "",
    "Description": "The amount of time after a message is received but not deleted that the message is hidden from other consumers"
  },
  {
    "Name": "Receive Message Wait Time",
    "Default Value": "0 sec",
    "Allowable Values": "",
    "Description": "The maximum amount of time to wait on a long polling receive call. Setting this to a value of 1 second or greater will reduce the number of SQS requests and decrease fetch latency at the cost of a constantly active thread."
  },
  {
    "Name": "Proxy Host",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "Proxy host name or IP\nSupports Expression Language: true"
  },
  {
    "Name": "Proxy Host Port",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "Proxy host port\nSupports Expression Language: true"
  }
]
```

```json
[
  {
    "Name": "Queue URL",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The URL of the queue to act upon\nSupports Expression Language: true"
  },
  {
    "Name": "Access Key",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "No Description Provided.\nSensitive Property: true\nSupports Expression Language: true"
  },
  {
    "Name": "Secret Key",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "No Description Provided.\nSensitive Property: true\nSupports Expression Language: true"
  },
  {
    "Name": "Credentials File",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "Path to a file containing AWS access key and secret key in properties file format."
  },
  {
    "Name": "AWS Credentials Provider service",
    "Default Value": "",
    "Allowable Values": "Controller Service API: \nAWSCredentialsProviderService\nImplementation:\nAWSCredentialsProviderControllerService",
    "Description": "The Controller Service that is used to obtain aws credentials provider"
  },
  {
    "Name": "Region",
    "Default Value": "us-west-2",
    "Allowable Values": "us-gov-west-1 \nus-east-1 \nus-west-1 \nus-west-2 \neu-west-1 \neu-central-1 \nap-southeast-1 \nap-southeast-2 \nap-northeast-1 \nap-northeast-2 \nsa-east-1 \ncn-north-1",
    "Description": "No Description Provided."
  },
  {
    "Name": "Delay",
    "Default Value": "0 secs",
    "Allowable Values": "",
    "Description": "The amount of time to delay the message before it becomes available to consumers"
  },
  {
    "Name": "Communications Timeout",
    "Default Value": "30 secs",
    "Allowable Values": "",
    "Description": "No Description Provided."
  },
  {
    "Name": "Proxy Host",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "Proxy host name or IP\nSupports Expression Language: true"
  },
  {
    "Name": "Proxy Host Port",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "Proxy host port\nSupports Expression Language: true"
  }
]
```

## Requesting Access

This integration is only available with a [Qordoba Enterprise](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html) subscription.

If you are not a Qordoba Enterprise customer, you can inquire about our
Enterprise offering by [contacting us](http://go.qordoba.com/WF-Request-A-Demo__LP-DevDocs-Header.html).
