# Nest On Openhab - Step-By Step Guide

Google announced their [Device Access Program](https://developers.google.com/nest/device-access) (September 2020) that allows users to access, control, and manage Google Nest devices using the Smart Device Management (SDM) API. SDM is replacement for the [Works With Nest](https://blog.google/products/google-nest/updates-works-with-nest/) program that was "retired" August 31, 2019 and no longer supported by Google as part of their acquisition of Nest.   

This guide is intended to document the steps needed to enable this API so that it can be connected to the [NestDeviceAcces Binding](https://github.com/bhigg-code/openhab-addons/tree/dev/bundles/org.openhab.binding.nestdeviceaccess).

##  Considerations: The Google SDM API with Nest Device Access Binding

- In order to use the SDM API, you will need to enable access to each of your supported devices.  If you are currently using the [OpenHab Nest Binding](https://www.openhab.org/addons/bindings/nest/) and "Works With Nest" to connect your devices to openHab, you would need to leave that program and migrate your Nest account to a Google account (i.e. your devices to the Google account).  

![Supported Devices](/doc/NestSupportedDevices.jpg)
**Note:** As of this writing, supported Nest devices do not include Nest Protects. 

2. The 


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
