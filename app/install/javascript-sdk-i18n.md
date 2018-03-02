---
id: page-install-method
title: Install - Qordoba Javascript SDK 
header_title: Install - Qordoba Javascript SDK 
header_icon: /assets/images/icons/icn-installation.svg
breadcrumbs:
  Installation: /install
links:
  aws: "https://console.aws.amazon.com/cloudformation/home"
  templates:
    kong-hvm: "https://s3.amazonaws.com/kong-cf-templates/latest/kong-elb-cassandra-user-vpc-optional-hvm.template"
    kong-pv: "https://s3.amazonaws.com/kong-cf-templates/latest/kong-elb-cassandra-user-vpc-optional-pv.template"
    kong-postgres-hvm: "https://s3.amazonaws.com/kong-cf-templates/latest/kong-elb-postgres-optional-vpc-optional-hvm.template"
    kong-postgres-pv: "https://s3.amazonaws.com/kong-cf-templates/latest/kong-elb-postgres-optional-vpc-optional-pv.template "
---

### Installation

1. **Create Project in Qordoba**

    To use Qordoba's SDK integration, you need to first create a SDK project in Qordoba. In Qordoba's UI, select the Projects dropdown menu, and select "+ Create new project" at the bottom of the list. Select a JS SDK project, add the url that the integration will be watching, and complete the steps selecting your languages and translation memories. On the final step of project creation, copy the code snippet provided and paste it somewhere for temporary storage.

2. **Add Snippet to HTML of Pages**

    Next, add the provided snippet within the <head> of all html pages that you will want the SDK to have access to. If you have individual pages or urls that you do not want the SDK to work with, you can set up this and other customizations in the SDK settings at a later point.

3. **Collect Strings From Your Site**

    Once the Qordoba code snippet has been added to your pages, you need to collect the english strings from those pages. There are two ways to collect strings using the SDK integration:
    
    1. **Manual selection of individual urls**<br>
    In your address bar, add the query `?force-collect=true` to the end of each url that you want to have translations for, and execute the url. If the SDK is loaded on a page when the query parameter is added, the SDK will scrape that page's html for all strings, and send the texts to Qordoba for translation. <br>
    _This option is likely your best solution if you have few separate url paths in your domain, or if you only want to translate a small portion of your urls using Qordoba. If you change or add to your website, you will have to re-collect each page that has changed again._

    2. **Automatic collection of pages**<br>
    The other way to collect is to add a parameter to your SDK settings in Qordoba. In Qordoba -> Settings -> SDK settings, add the key-value pair of `liveSyncPages: true` to the settings. Once you have done this, all you have to do is visit pages that are within the domain that you originally linked the project to, and the SDK will automatically scrape the pages for strings and send them to Qordoba.<br>
    _This option is easier to use than the manual selection, but you lose some control over what pages get sent to Qordoba. If there are a few specific pages that you do not want translated, you can always tag them as "disabled" within Qordoba which will prevent any work on them. If you change or update your website, the very first time anyone visits each updated page, the new strings will be sent to Qordoba._


    _**Note:** Qordoba's SDK integration is able to collect from dynamic content, however the elements must exist in the html for the SDK to collect them. If you have dynamic content that you want Qordoba to translate, simply complete the actions necessary on your page to have that content appear in the html. Once it does, Qordoba will collect it and will replace it if there are completed translations._

4. **Complete Translations in Qordoba**

    The next step is to complete your strings in Qordoba and publish the translated strings for each locale. When you have completed translations for each segment for any given url path, Qordoba will automatically take those strings and publish them so they are available to replace your english content. You will know that a file is finished with translations when you see a green "Completed" button in the UI, and a "Published" symbol next to it.

5. **View Translated Material on Your Website**

    The final step is to tell the SDK integration to display the translated text in place of the source language text. You can configure this command in a number of ways in the url, by setting up your desired url pathing in the SDK settings. This is best done with support from Qordoba's Customer Success team, so for the purposes of this quick install there is a parameter you can add to the url to see Qordoba's translations. In your address bar, add the desired url followed by the parameter `?lang=<locale>`, where `<locale>` is the language code of your desired target language. For example: for Spanish - Mexico is `?lang=es-mx`. A full list of language codes can be found [here](https://dev.qordoba.com/docs/language-resource-dev). When you add the parameter and execute the url, if you have translated material Qordoba will automatically replace all source language strings on your page with the translated material.

##### PV AMI

- [us-east-1]({{ page.links.aws }}?region=us-east-1#/stacks/new?stackName=kong-elb-pv&templateURL={{ page.links.templates.kong-pv }})
- [us-west-1]({{ page.links.aws }}?region=us-west-1#/stacks/new?stackName=kong-elb-pv&templateURL={{ page.links.templates.kong-pv }})
- [us-west-2]({{ page.links.aws }}?region=us-west-2#/stacks/new?stackName=kong-elb-pv&templateURL={{ page.links.templates.kong-pv }})
- [eu-west-1]({{ page.links.aws }}?region=eu-west-1#/stacks/new?stackName=kong-elb-pv&templateURL={{ page.links.templates.kong-pv }})
- [ap-northeast-1]({{ page.links.aws }}?region=ap-northeast-1#/stacks/new?stackName=kong-elb-pv&templateURL={{ page.links.templates.kong-pv }})
- [ap-southeast-1]({{ page.links.aws }}?region=ap-southeast-1#/stacks/new?stackName=kong-elb-pv&templateURL={{ page.links.templates.kong-pv }})
- [ap-southeast-2]({{ page.links.aws }}?region=ap-southeast-2#/stacks/new?stackName=kong-elb-pv&templateURL={{ page.links.templates.kong-pv }})
- [sa-east-1]({{ page.links.aws }}?region=sa-east-1#/stacks/new?stackName=kong-elb-pv&templateURL={{ page.links.templates.kong-pv }})

#### Kong with PostgreSQL

This template will provision Kong instances in a new or existing VPC. You can
provide your own PostgreSQL instance, or if not, the template will create one
on AWS RDS for you.

##### HVM AMI

- [us-east-1]({{ page.links.aws }}?region=us-east-1#/stacks/new?stackName=kong-elb-postgres-hvm&templateURL={{ page.links.templates.kong-postgres-hvm }})
- [us-west-1]({{ page.links.aws }}?region=us-west-1#/stacks/new?stackName=kong-elb-postgres-hvm&templateURL={{ page.links.templates.kong-postgres-hvm }})
- [us-west-2]({{ page.links.aws }}?region=us-west-2#/stacks/new?stackName=kong-elb-postgres-hvm&templateURL={{ page.links.templates.kong-postgres-hvm }})
- [eu-west-1]({{ page.links.aws }}?region=eu-west-1#/stacks/new?stackName=kong-elb-postgres-hvm&templateURL={{ page.links.templates.kong-postgres-hvm }})
- [ap-northeast-1]({{ page.links.aws }}?region=ap-northeast-1#/stacks/new?stackName=kong-elb-postgres-hvm&templateURL={{ page.links.templates.kong-postgres-hvm }})
- [ap-southeast-1]({{ page.links.aws }}?region=ap-southeast-1#/stacks/new?stackName=kong-elb-postgres-hvm&templateURL={{ page.links.templates.kong-postgres-hvm }})
- [ap-southeast-2]({{ page.links.aws }}?region=ap-southeast-2#/stacks/new?stackName=kong-elb-postgres-hvm&templateURL={{ page.links.templates.kong-postgres-hvm }})
- [sa-east-1]({{ page.links.aws }}?region=sa-east-1#/stacks/new?stackName=kong-elb-hvm&templateURL={{ page.links.templates.kong-postgres-hvm }})

##### PV AMI

- [us-east-1]({{ page.links.aws }}?region=us-east-1#/stacks/new?stackName=kong-elb-postgres-pv&templateURL={{ page.links.templates.kong-postgres-pv }})
- [us-west-1]({{ page.links.aws }}?region=us-west-1#/stacks/new?stackName=kong-elb-postgres-pv&templateURL={{ page.links.templates.kong-postgres-pv }})
- [us-west-2]({{ page.links.aws }}?region=us-west-2#/stacks/new?stackName=kong-elb-postgres-pv&templateURL={{ page.links.templates.kong-postgres-pv }})
- [eu-west-1]({{ page.links.aws }}?region=eu-west-1#/stacks/new?stackName=kong-elb-postgres-pv&templateURL={{ page.links.templates.kong-postgres-pv }})
- [ap-northeast-1]({{ page.links.aws }}?region=ap-northeast-1#/stacks/new?stackName=kong-elb-postgres-pv&templateURL={{ page.links.templates.kong-postgres-pv }})
- [ap-southeast-1]({{ page.links.aws }}?region=ap-southeast-1#/stacks/new?stackName=kong-elb-postgres-pv&templateURL={{ page.links.templates.kong-postgres-pv }})
- [ap-southeast-2]({{ page.links.aws }}?region=ap-southeast-2#/stacks/new?stackName=kong-elb-postgres-pv&templateURL={{ page.links.templates.kong-postgres-pv }})
- [sa-east-1]({{ page.links.aws }}?region=sa-east-1#/stacks/new?stackName=kong-elb-postgres-pv&templateURL={{ page.links.templates.kong-postgres-pv }})

----
### Recommended usage

  <B>Use this cloud formation as a basis for your own, adjust the variables and template to better suit your needs.</B>
----

### Instructions

1. **Initial Setup**

    Create the required key pair to access your Kong instances. If you are
    providing your own Cassandra/PostgreSQL instances, make sure they are
    accessible from your Kong instances. If you want to create instances in
    an existing VPC, this VPC needs to have two public subnets, and all
    required ports open to allow access to the Kong Load Balancer.

    *Continue to next step if you want to use an existing key pair*

3. **Choose a Region & VM Type**

    Choose the region closest to your API servers, and pick the virtualization
    type you'd like from the list of available [templates](#templates) above.

    You should land on AWS Cloud Formation *"Select Template"* page

4. **Parameters**

    Fill-in all the parameters details. If you chose to launch Kong with
    PostgreSQL but without specifying your own PostgreSQL server, you will be
    asked to fill-in a few extra parameters to create a PostgreSQL RDS
    instance. Check the description of each field and provide the appropriate
    values.

    **Note**: *consult the [templates documentation on Github]({{ site.repos.cloudformation }}) for detailed description of parameters*

5. **Option page**

    Add Tags and other fields according to your requirements.

    **Note:** *The template is configured to add a "Name" tag to each relevant resource*

5. **Template Documentation**

    For more details on parameters and futher configuration options, please consult the [templates documentation on Github]({{ site.repos.cloudformation }})

6. **Grab a Coffee!**

    It will take several minutes *(~20 minutes)* to create the stack. Once the stack has a status of `CREATE_COMPLETE`, click on the *"Output"* tab to get the Proxy and Admin URLs, it may take *60 more seconds* for the links to become active.

    **Note**: *To monitor the progress go to AWS CloudFormation console, select the stack in the list. In the stack details pane, click the "Events" tab to see the progress.*

    <div class="alert alert-warning">
      <div class="text-center">
        <strong>Note</strong>: Check out the <a href="{{ site.repos.cloudformation }}">kong-dist-cloudformation</a> repository for further details.
      </div>
    </div>

7. **Use Kong**

    Quickly learn how to use Kong with the [5-minute Quickstart](/docs/latest/getting-started/quickstart).
