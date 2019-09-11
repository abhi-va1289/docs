---
title: "WaveMaker Application deployment to WebLogic application server"
id: ""
---

WaveMaker Apps can be exported as a WAR file. This generated file can be deployed to any standard Java Web Server running on JDK 1.8. You can know more about [Deployment to Web Server](/learn/app-development/deployment/deployment-web-server/) from here.

This section walks through the steps to deploy WaveMaker app to Oracle WebLogic Server.

## Pre-requisites

1. WebLogic Server needs to installed in the system. [Refer here](http://www.oracle.com/technetwork/middleware/weblogic/downloads/wls-main-097127.html) for installation. **Note:** The following instructions are for deployment to **WebLogic Server 11g (10.3.6)**.
2. Prepare WebLogic XML for defining classloading policies and other instructions.
3. WaveMaker application (war) file. The following instructions assume the war file is named **SampleApp.war, **change the name as per your use case.

## Steps Involved

1. [Setting](#xmlfile) WebLogic.xml file in project
2. [Create](#warfile) Application War file for WaveMaker app
3. [Deploy](#deployment) Application (Deployment Process)

## Setting WebLogic XML file in project

1. Download the following [zip file](../assets/weblogic.zip) and extract the WebLogic XML file.
2. Open the WaveMaker app and [Import the extracted _weblogic.xml_ file](http://[supsystic-show-popup id=112]) into project. Make sure it is imported to the following location: \[project\_home\]/src/main/webapp/web-inf[![](../assets/weblogic1.png)](../assets/weblogic1.png)

## Create Application War file

[Export Project](http://[supsystic-show-popup id=116]) as war. [See here](/learn/app-development/deployment/deployment-web-server/#war-file-generation) for steps in war file generation for WaveMaker apps.

## Deploy Application to WebLogic (Deployment Process)

1. Log in to WebLogic server
2. From the _Deployments_ section (link on the left side menu), click the _Install_ button.[![](../assets/weblogic2.png)](../assets/weblogic2.png)
3. Provide the path to the location of war file in the _Path_ text box, select the _war file_ and click the _Next_ button.[![](../assets/weblogic3.png)](../assets/weblogic3.png)
4. Select '_Install this deployment as an application_' and click the _Next_ button.[![](../assets/weblogic4.png)](../assets/weblogic4.png)
5. Provide the app _Name_ and click the _Next_ button.[![](../assets/weblogic5.png)](../assets/weblogic5.png)
6. Select '_Yes, take me to the deployment's configuration screen_' and click the _Finish_ button.[![](../assets/weblogic6.png)](../assets/weblogic6.png)
7. Click the _Save_ button in deployment settings page[![](../assets/weblogic7.png)](../assets/weblogic7.png)
8. Select the _Testing_ tab to access the deployed application.[![](../assets/weblogic8.png)](../assets/weblogic8.png)

**Deployment to WebLogic**

- [i. Prerequisites](#prerequisites)
- [ii. Steps Overview](#steps)
    - [○ Setting WebLogic xml file](#xmlfile)
    - [○ Generating app war file](#warfile)
    - [○ Deployment Process](#deployment)