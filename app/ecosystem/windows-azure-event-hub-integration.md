---
id: page-plugin
title: Qordoba - Windows Azure event hub integration
header_title: Qordoba - Windows Azure event hub integration
header_icon: /assets/images/icons/plugins/windows-azure-event-hub-integration.png
breadcrumbs:
  Plugins: /plugins
nav:
  - label: Getting Started
    items:
      - label: Requesting Access
---
Receives messages from a Microsoft Azure Event Hub, writing the contents of the Azure message to Qordoba content Editor. And after you finish the translations/l10n process you can sends the contents to a Windows Azure Event Hub or use Qordoba APIs/CLI to download the content.

```
[
  {
    "Name": "Event Hub Name",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The name of the Azure Event Hub to pull messages from"
  },
  {
    "Name": "Event Hub Namespace",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The Azure Namespace that the Event Hub is assigned to. This is generally equal to <Event Hub Name>-ns"
  },
  {
    "Name": "Shared Access Policy Name",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The name of the Event Hub Shared Access Policy. This Policy must have Listen permissions."
  },
  {
    "Name": "Shared Access Policy Primary Key",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The primary key of the Event Hub Shared Access Policy\nSensitive Property: true"
  },
  {
    "Name": "Number of Event Hub Partitions",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The number of partitions that the Event Hub has. Only this number of partitions will be used, so it is important to ensure that if the number of partitions changes that this value be updated. Otherwise, some messages may not be consumed."
  },
  {
    "Name": "Event Hub Consumer Group",
    "Default Value": "$Default",
    "Allowable Values": "",
    "Description": "The name of the Event Hub Consumer Group to use when pulling events"
  },
  {
    "Name": "Event Hub Message Enqueue Time",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "A timestamp (ISO-8061 Instant) formatted as YYYY-MM-DDThhmmss.sssZ (2016-01-01T01:01:01.000Z) from which messages should have been enqueued in the EventHub to start reading from"
  },
  {
    "Name": "Partition Recivier Fetch Size",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The number of events that a receiver should fetch from an EventHubs partition before returning. Default(100)"
  },
  {
    "Name": "Partiton Receiver Timeout (millseconds)",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The amount of time a Partition Receiver should wait to receive the Fetch Size before returning. Default(60000)"
  }
]
```

```
[
  {
    "Name": "Event Hub Name",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The name of the Azure Event Hub to send to"
  },
  {
    "Name": "Event Hub Namespace",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The Azure Namespace that the Event Hub is assigned to. This is generally equal to <Event Hub Name>-ns"
  },
  {
    "Name": "Shared Access Policy Name",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The name of the Event Hub Shared Access Policy. This Policy must have Send permissions."
  },
  {
    "Name": "Shared Access Policy Primary Key",
    "Default Value": "",
    "Allowable Values": "",
    "Description": "The primary key of the Event Hub Shared Access Policy\nSensitive Property: true"
  }
]
```

```
The content of the Windows Azure Event should not be more than 500KB per massages, so care should be taken to avoid the limitations
```
