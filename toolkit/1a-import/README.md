# Import your API spec, and proxy an existing REST service
Duration: 5 mins  
Skill level: Beginner  


### Objective
This tutorial is to help you get started quickly with **API Connect** by illustrating how you can bring your existing API under management control. We'll start by importing an OpenAPI spec, and then create a passthrough API proxy for an existing REST service.

---


### Explore the sample app, and test the target endpoints
A sample _weather provider_ app has been created for this tutorial
- Explore this app here: http://gettingstartedweatherapp.mybluemix.net/
- Enter a valid 5-digit US zipcode to get the _**current weather**_ and _**today's forecast**_  
![](/bluemix/1a/images/explore-weatherapp-1.png)

  - Endpoint to get the **current** weather data is:     _**https:// myweatherprovider<span></span>.mybluemix.net/current?zipcode={zipcode}**_
  - Test it out by clicking: https://myweatherprovider.mybluemix.net/current?zipcode=90210  
  ![](/bluemix/1a/images/explore-weatherapp-2.png)

  - Endpoint to get **today's** forecast data is:  
   _**https:// myweatherprovider<span></span>.mybluemix.net/today?zipcode={zipcode}**_
  - Test it out by clicking: https://myweatherprovider.mybluemix.net/today?zipcode=90210  
  ![](/bluemix/1a/images/explore-weatherapp-3.png)


---

### Import the sample app's OpenAPI spec to create a REST API proxy
- Launch the **API Designer**
  - In your terminal, enter `apic edit`
  - Log in using your IBMid
    ![](images/screenshot_apic-edit_login.png)
  - In the **API Designer** navigation panel (left hand), click on **Drafts > APIs**
  - In the **APIs** panel, click on **Add > Import API from a file or URL**
  - In the "Import OpenAPI (Swagger) dialog box that pops up, enter this URL:
https://raw.githubusercontent.com/ibm-apiconnect/getting-started/master/toolkit/1a-import/weather-provider-api_1.0.0.yaml
  - Leave the _Add a product_ option **unchecked**, and click **IMPORT**  
    ![](images/screenshot_import-url.png)  






- There are a few more steps before your API proxy is ready
- In the API's **Design** view, scroll down to the **Host** panel.   
_You'll notice that the Host value is set to myweatherprovider.mybluemix.net. Change this value to_ ```$(catalog.host)``` _. By doing so, you are setting the base URL for your API proxy._
- Save your API  




### Test your API proxy
###### Test with the _API Manager test tool_
- Swith over to the **Assemble** tab,
  - Start the local test server by clicking on **Start servers** icon at the bottom of the screenshot_start-server-1
    ![](images/screenshot_start-server-1.png)

- Click ► to test your API proxy's target invocation
    ![](images/screenshot_test-0.png)

  - In the test panel, select the **get /current** operation.  
  - Zipcode is a required parameter for this operation, so enter a valid US zip (e.g. 90210).  
  - Click **invoke**, and verify that you see:
    - 200 OK response
    - Current weather data for 90210  
    ![](images/screenshot_test-1.gif)  


###### Test with the _Explore tool_  
- To test your API proxy endpoints
  - Click the _Explore_ button
  - Click on the **GET /current** operation from the palette
  - Enter a valid US zipcode (e.g. 90210) in the test box
  - Click **Call operation** to see the response  
  ![](images/screenshot_explore.png)
