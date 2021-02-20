# Nest On openHAB - Step-By Step Guide

Google announced the availability of their [Device Access Program](https://developers.google.com/nest/device-access) (September 2020) that allows users to access, control, and manage Google Nest devices using the Smart Device Management (SDM) API. The SDM API is the replacement for the [Works With Nest](https://blog.google/products/google-nest/updates-works-with-nest/) program that was "retired" August 31, 2019 and no longer supported by Google as part of their acquisition of Nest.   

This guide is intended to document the steps needed to enable this API so that it can be connected to the [NestDeviceAcces Binding](https://github.com/bhigg-code/openhab-addons/tree/dev/bundles/org.openhab.binding.nestdeviceaccess).

##  Considerations: The Google SDM API with Nest Device Access Binding

**1.** In order to use the SDM API, you will need to enable access to each of your supported devices.  If you are currently using the [OpenHAB Nest Binding](https://www.openhab.org/addons/bindings/nest/) and "Works With Nest" to connect your devices to openHAB, you would need to leave that program and migrate your Nest account to a Google account (i.e. your devices to the Google account). _Once you migrate accounts, this cannot be un-done!_

Information on migrating your Nest account can be found here - [FAQs about accounts for the Nest app](https://support.google.com/googlenest/answer/9297676?co=GENIE.Platform%3DiOS&hl=en&oco=0#accountmigration&accountmigration1&#accountmigration2&#accountmigration3&zippy=%2Chow-do-i-migrate-my-account).  Look for the FAQ titled "Migrating your Nest Account to a Google Account" and expand the FAQ to find the sub-topic titled "How do I migrate my account?"
 
**Supported Device List**
| [Nest Thermostat](https://developers.google.com/nest/device-access/api/thermostat)| [Nest Cam](https://developers.google.com/nest/device-access/api/camera) | [Nest Hello Doorbell](https://developers.google.com/nest/device-access/api/doorbell) | [Nest Hub Max](https://developers.google.com/nest/device-access/api/display)|
| --------------------- | ------------------- | -------------------- | --------------------|
| ![Thermostat](/doc/device-thermostat_480.png) | ![Camera](/doc/device-camera_480.png) | ![Hello](/doc/device-hello_480.png) | ![Hub](/doc/device-hub-max_480.png) |
| Read state and change thermostat modes and setpoints. | Access camera livestreams and camera events | Know when the doorbell is pressed and see the related camera snapshot. | Access camera features of the display, such as livestreams and camera events. |
| [Thermostat guide](https://developers.google.com/nest/device-access/api/thermostat) | [Camera guide](https://developers.google.com/nest/device-access/api/camera) | [Doorbell guide](https://developers.google.com/nest/device-access/api/doorbell) | [Display guide](https://developers.google.com/nest/device-access/api/display) |
 
> **Note:** As of this writing, supported devices do not include Nest Protects. 

**2.** The Nest Device Access binding is under development.  It has been tested with thermostats; other API supported devices (camera and doorbell) are implemented but still require additional testing.  

**3.** The good news is that there is a plan to port this binding to OpenHAB 3. Until this is complete, these instructions assume you will install the NestDeviceAccess binding in a stable V2 release of openHAB.

**4.** Finally some basic assumptions to be sure you are prepared to move forward:
- Strongly recommend you have an environment you can test with
- You will need to have a basic understanding of how to read the logs, debug and be willing help test/troubleshoot
- Provide feedback about your experience on the openHab Community forum for this [Topic](https://community.openhab.org/t/google-nest-device-access-console-now-available/105404)
- Basic understanding of Linux command line interface (CLI)
  - Access and ability to execute commands on your system 
  - Setting up the SDM API requires you to execute Curl commands to retrieve/refresh authorization keys and tokens
  - You will want to execute Curl commands to test access to your enabled devices and view their settings

## Step-By Step

The majority of this content is consolidated from the Google sites that walk you through the SDM setup steps to enable the API. These instructions will follow Google's outline and will hopefully remove some of the head scratching I went through trying to complete each step.

### Step 1.0 - Register for Device Access
If you have not already done this, follow the link to the Device Access Console below.  You will be setting up a device access sandbox account, and Yes, there is a one-time fee of $5.00 USD to set up device access (not unreasonable).  

> Before creating your first project, you must register for Device Access. Registration consists of the acceptance of the Google API and Device Access Sandbox Terms >of Service, along with a one-time, non-refundable fee (US$5) per account.
>
>You will not be able to create a project until you have accepted both Terms of Service and paid the registration fee. This applies to all users, both individual >users and those looking to create a commercial offering.
>
>Register in the Device Access Console, if you haven't already: [Go to the Device Access Console](https://console.nest.google.com/device-access)

Once you have registered you should have access to the Console and see a "card" to create (add) a new project.  So far so good...

![Device Access Console](/doc/Device-Access-Console-1_250.png)

## Step 2.0 - Activate a Supported Nest Device with a Google Account

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/dschoepel/NestOnOpenhab/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
