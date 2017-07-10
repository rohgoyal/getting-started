---

copyright:
years: 2017
lastupdated: "2017-07-10"

---
# Managing a SOAP service
**Duration**: 15 mins
**Skill level**: Beginner

---
### Objective
In API Manager, you will create a SOAP API that is a proxy for a SOAP-based weather service.

### Prerequisites
- Before you begin, you will need to [set up your API Connect instance](https://github.com/ibm-apiconnect/getting-started/blob/master/bluemix/0-prereq/README.md)
- Before you begin, copy the WSDL file located at https://github.com/ibm-apiconnect/getting-started/blob/master/bluemix/manage-soap-api/files/weatherprovider.wsdl to your local filesystem.
Note : You can click **Raw** and then save the resulting page on your local system as a `.wsdl` file.

---
### Setting up a SOAP API definition
1. Log in to IBM Bluemix: https://new-console.ng.bluemix.net/login.

2. In the Bluemix **Dashboard** scroll down and select API Connect. Alternately, from the menu icon, choose **Services** and then **APIs** to reach the **Work with APIs** window, and select **API Connect**. From the **API Connect** page, you can simply press `Create`, or you can adjust the default settings. For the purposes of this exercise, leave the instance unbound, and adjust the Service name for easier recognition later. One example would be `API Connect-weather-exercise`.
Press the `Create` button to launch the API Connect service.  
You may see an alert describing what's new, or the **Draft APIs** informational splash page shown in the following image. After reading the information click the **"Got it"** icon to view the API Manager.
![Draft APIs splash page](images/apic_draft-apis.png)

3. On your first visit to the API Manager, a helpful task list appears in the UI. You can select `01 Import API` from this list, or click `Add +` in the main window to view the APIs panel.

4. In the APIs panel, select **API from SOAP service**.

![](images/newapi-menu2.png)

5. The New API from WSDL dialog box opens. Click **Upload File**.
![](images/4-uploadwsdl.png)

6. Select the ```weatherprovider.wsdl``` file that you saved previously.

7. The New API from WSDL dialog box reappears. Check the **weatherService** check box. Click **Done**.
![](images/newapi2.png)

8.Your API is now created. The `API Editor` page displays. Notice that the `Getting started` task list now indicates the step you are on **02 Generate and Publish**.

![](images/designpage2.png)

9.	Scroll down to the **Security tab**, and click the delete icon to remove the `clientIDHeader (API Key)` that was automatically generated when you created the service.

10.	Click the ![save](images/save.png) icon to save your changes. An "API Saved" appears momentarily.

11.	In the menu bar with the save icon, the **Design** indicates your present location. Next to that, you find the **Source** tab where you can directly view the Swagger (2.0) file that represents your API, and next to that, you find the **Assemble** tab that takes you to a drag and drop interface for API processing. Click **Assemble**.
![](images/assemble-clean.png)

---
### Testing the SOAP API definition
1. In the **Assemble** tab, click the **More actions** (three dots) icon, and select **Generate a default product** from the menu.
   ![](images/gen-default-prod.png)

2. Accept the default options in the **New Product** dialog pop-up, and select **Create Product**. The **weatherService product 1.0.0** is created and published to the Sandbox catalog.
  ![](images/12a-chooseproduct.png)

  - _In API Connect, **Products** provide a mechanism to  group APIs that are intended for a particular use. Products are published to a **Catalog**. [Reference: API Connect glossary]_

3. Save your changes.
4. Next to the Search box, click the test icon ► to test the API service. ![]() The Setup menu appears.

5. From the Products list, choose ```weatherService product 1.0.0```.
![](images/12-chooseproduct.png)

6.	Scroll to the bottom and click **Next**.

7.	From the list of Operations, select ```post /weatherRequest```.
![](images/13-selectoperation.png)

8.	Scroll down. Enter the following xml in the body field. You can select and copy the following example XML, then click the **body** field to activate the field and place the example XML.
```
<?xml version="1.0" encoding="UTF-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
   <soap:Body>
<wdata:WeatherRequest xmlns:wdata="http://www.ibm.com/wdata">
       <zipcode>01742</zipcode>
</wdata:WeatherRequest>
   </soap:Body>
</soap:Envelope>
```

![](images/14-enterrequest.png)

9.	Scroll down if needed, and click **Invoke**.
The API returns a Response **body** consisting of the current weather.
![](images/15-success.png)

### What you did in this tutorial
In this tutorial, you completed the following:
1. Set up a SOAP API definition
2. Tested your API definition
3. Received a Response **body** from the weather API endpoint indicating the result of your Request.
