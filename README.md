# Nest On openHAB - Step By Step Guide

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

**3.** The good news is that this binding has been ported to OpenHAB 3 and updated to inlcude the SDM API. These instructions assume you will install the NestDeviceAccess binding in a V3 release of openHAB using the SDM configuration.

**4.** Finally some basic assumptions to be sure you are prepared to move forward:
- Strongly recommend you have an environment you can test with
- You will need to have a basic understanding of how to read the logs, debug and be willing help test/troubleshoot
- Provide feedback about your experience on the openHab Community forum for this [Topic](https://community.openhab.org/t/google-nest-device-access-console-now-available/105404)
- Basic understanding of Linux command line interface (CLI)
  - Access and ability to execute commands on your system 
  - Setting up the SDM API requires you to execute commands to retrieve/refresh authorization keys and tokens
  - You may want to execute Curl commands to test access to your enabled devices and view their settings

### Step-by-Step Instructions

> Head on over to the [**Wiki**](https://github.com/dschoepel/NestOnOpenhab/wiki) for the detailed instructions.  

My intent is to improve/keep this information up to-date.  Constructive feedback is always welcome and can be provided on openHab's Community forum for this [Topic](https://community.openhab.org/t/google-nest-device-access-console-now-available/105404).
