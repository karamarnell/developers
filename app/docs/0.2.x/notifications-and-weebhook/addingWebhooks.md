---
title: Adding Webhooks
---

#Qordoba's Webhooks are simply put: Powerful Messages.

###You can leverage them in two ways: 

  1. You can send them to Slack, which has a built-in way to digest webhook data that it receives. You can do this by setting up the webhook in Qordoba.

  2. You can send the Webhook to anywhere as a JSON payload, and once that webhook arrives at its destination, the customer can write code (or we can help  - simply email Support@qordoba.com) to open up the webhook (in order to receive the message). This is how companies can operate webhooks with Jira for example.
  We leverage slack for Webhooks but if you have a different messaging platform, it is possible to send our webhooks there with a little effort.
  
  **For more information on Slack Webhooks see below:**
  
    #####Incoming WebHooks for Slack:
    
      - Incoming Webhooks are a type of integration that makes it easy to post Slack messages from outside sources into your workspace. This is a great way to send data to your workspace in real-time.

      - Here’s how they work: Incoming Webhooks make use of normal HTTP requests (sent using the POST method) with a JSON payload that includes a message and some additional options — such as a message icon, channel overrides, and author information, to name a few. 

      Tip: Curious about HTTP requests? Check out this [HTTP Tutorial](https://www.tutorialspoint.com/http/index.htm) 
      
    #####Setting up Incoming Webhooks with Slack: 

      1. Choose the channel your Incoming WebHook will post messages to.
      
      2. Make sure you rename the Webhook "Qordoba-Webhook"
      
      3. Click Add Incoming WebHooks Integration.
      
      4. Click Save Settings to finish [Screencast](https://www.screencast.com/t/qYqQvjzwGs)
      
      5. Visit the Incoming WebHooks page in the Slack App Directory.
      
      6. Click Add Configuration.  
