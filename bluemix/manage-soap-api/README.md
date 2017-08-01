---

copyright:
years: 2017
lastupdated: "2017-07-11"

---
# Managing a SOAP service with IBM Bluemix
**Duration**: 15 mins  
**Skill level**: Beginner


## Objective
In API Manager, you will create a SOAP API that is a proxy for a SOAP-based weather service.

## Prerequisites
- Before you begin, you will need to [set up your API Connect instance](https://github.com/ibm-apiconnect/getting-started/blob/master/bluemix/0-prereq/README.md)
- Before you begin, copy the WSDL file located at https://github.com/ibm-apiconnect/getting-started/blob/master/bluemix/manage-soap-api/files/weatherprovider.wsdl to your local filesystem.
Note : You can click **Raw** and then save the resulting page on your local system as a `.wsdl` file. As the name suggest this SOAP service returns weather data given an zipcode.

---


## Setting up a SOAP API definition
1. Log in to IBM Bluemix: https://new-console.ng.bluemix.net/login.
2. Once logged in to Bluemix, scroll down to **All Services**, and click on **API Connect**. 
3. Click on **API Connect** to launch the API Connect service.  
  ![](images/bluemix-launch-apic.png)  
  
4. In the API Connect interface, make sure the navigation panel on the left side is open. If not, click **>>** to open it.  
5. Click on **Drafts** in the navigation panel.   
6. Go to the **APIs** tab
7. In the **APIs** tab, click **Add**
8. In the dropdown menu, click **API from SOAP service**.
   ![New API](images/newapi-menu2.png)

9. The New API from WSDL dialog box opens. Click **Upload File**.
![upload the .wsdl file](images/4-uploadwsdl.png)

10. Select the ```weatherprovider.wsdl``` file that you saved previously.

11. The New API from WSDL dialog box reappears. Check the **weatherService** check box. Click **Done**.
![select weather service](images/newapi2.png)

12.On successful import, you are taken to the **Design** view of the API. Also you can view the OpenAPI definition under **Source** tab.
  > _In the Source tab, you'll see that the wsdl is wrapped inside the OpenAPI definition._

![API Editor page](images/designpage2.png)

13.	Scroll down to the **Security** tab, and click the delete icon to remove the `clientIDHeader (API Key)` that was automatically generated when you created the service.
> _You will cover security with API Keys in the next tutorial._ 

14.	Save your API by clicking the ![save](images/save.png) icon on the top right corner of the designer. An "API Saved" confirmation notification appears momentarily.

15.	In the menu bar with the save icon, the **Design** tab indicates your present location. Next to that, you find the **Source** tab where you can directly view the Swagger (2.0) file that represents your API, and next to that, you find the **Assemble** tab that takes you to a drag and drop interface for API processing. Click **Assemble**.
![Assemble tab](images/assemble-clean.png)

---


### Testing the SOAP API definition
1. Naviage to **Assemble** tab, click on More Actions (three dots overflow menu icon) then click Generate a default product.  
   ![More actions menu, open](images/gen-default-prod.png)

2. Accept the default options in the **New Product** dialog pop-up, and select **Create Product**. The **weatherService product 1.0.0** is created and published to the Sandbox catalog.
  ![create a new product](images/12a-chooseproduct.png)

 >_In API Connect, **Products** provide a way to  group APIs that are intended for a particular use. Products are published to a **Catalog**. Reference: ![API Connect glossary](https://www.ibm.com/support/knowledgecenter/en/SSMNED_5.0.0/com.ibm.apic.overview.doc/overview_apimgmt_glossary.html)_

3. Save your changes.  

4. Next to the Search box, click the test icon ► to test the API service. The Setup menu appears.

5. From the Products list, choose ```weatherService product 1.0.0```.
![choose weather service](images/12-chooseproduct.png)

6.	Scroll to the bottom and click **Next**.

7.	From the list of Operations, select ```post /weatherRequest```.
![post a request](images/13-selectoperation.png)

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

![the request](images/14-enterrequest.png)

9.	Scroll down if needed, and click **Invoke**.
The API returns a Response **body** consisting of the current weather.
![](images/15-success.png)

### What you did in this tutorial
In this tutorial, you completed the following:
1. Set up a SOAP API definition
2. Tested your API definition
3. Received a Response **body** from the weather API endpoint indicating the result of your Request.
