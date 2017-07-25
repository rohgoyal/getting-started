# Import your API spec, and proxy an existing REST service with IBM API Connect toolkit 
**Duration:** 5 mins  
**Skill level:** Beginner  

## Objective
This tutorial helps you get started quickly with IBM API Connect by illustrating how you can bring your existing API under management control. You'll start by importing an OpenAPI spec, and then create a passthrough API proxy for an existing REST service.  

## Prerequisites
Before you begin, you will need to <a href="https://github.com/ibm-apiconnect/getting-started/tree/master/bluemix/0-prereq" target="blank">set up your API Connect instance</a> and <a href="https://github.com/ibm-apiconnect/getting-started/blob/master/toolkit/0-Prereq" target="blank">install the API Connect toolkit</a>.  

---

## Explore the sample app and test the target endpoints
A sample _weather provider_ app has been created for this tutorial. Its corresponding API specification (Swagger 2.0) can be found ![here](https://raw.githubusercontent.com/ibm-apiconnect/getting-started/master/bluemix/1a/weather-provider-api_1.0.0.yaml).
1. To explore the app, go to http://gettingstartedweatherapp.mybluemix.net/.  
2. Enter a valid 5-digit U.S. zipcode to get the _**current weather**_ and _**today's forecast**_.  
  ![](images/explore-weatherapp-1.png)

3. The above sample weather app was built using APIs that provide the weather data. The endpoint to get the **current** weather data is _**https:// myweatherprovider<span></span>.mybluemix.net/current?zipcode={zipcode}**_. Test it out by visiting https://myweatherprovider.mybluemix.net/current?zipcode=90210.  
  ![](images/explore-weatherapp-2.png)

4. Similarly, the Endpoint to get **today's** forecast data is _**https:// myweatherprovider<span></span>.mybluemix.net/today?zipcode={zipcode}**_. Test it out by going to https://myweatherprovider.mybluemix.net/today?zipcode=90210.  
  ![](images/explore-weatherapp-3.png)


---

## Import the sample app's OpenAPI spec to create a REST API proxy
1. Launch the **API Designer**. In your terminal window, enter the following command: `apic edit`.
2. Log in using your IBMid.
    ![](images/screenshot_apic-edit_login.png)
3. In the **API Designer**, ensure that the navigation panel is open. If not, click **>>** to open it.  
4. In the navigation panel, click **Drafts**.  
5. Then go to the **APIs** tab.
6. In the **APIs** tab, click **Add**
7. From the drop-down menu, click **Import API from a file or URL**.  
    ![](images/toolkit-import-1.png)

8. In the "Import OpenAPI (Swagger)" dialog box, enter the following URL:
https://raw.githubusercontent.com/ibm-apiconnect/getting-started/master/toolkit/1a-import/weather-provider-api_1.0.0.yaml. Leave the _Add a product_ option unchecked and click **Import**.  
    ![](images/screenshot_import-url.png)  
9. Once you import the OpenAPI spec, you are taken to the Design view of the API. Here you can view various sections of the OpenAPI definition. Scroll to explore, and especially note the Host value. Also you can view the OpenAPI under source tab.
   > _You'll see that the Host value is set to_ ```$(catalog.host)``` _. This is the base URL for your API proxy._
 
---

## Test your API proxy

1. Start the local test server by clicking the **Start servers** icon on the bottom left of the designer. Once the Gateway is started, you would see the status update automatically to _**Running**_
    ![](images/screenshot_start-server-1.png)
 
2. Switch over to the **Assemble** tab.

3. Click the play icon (►) to test your API proxy's target invocation.
    > _For this tutorial, we shall use the embedded Micro Gateway, so ensure Micro Gateway Policies is selected._
    
    ![](images/screenshot_test-0.png)

4. In the test panel:   
   a. Choose the **get /current** operation.  
   b. Zipcode is a required parameter for this operation, so enter a valid U.S. zip code (for example, 90210).  
   c. Click **invoke**, and verify the response.  
   > _If you run into a CORS error, follow the instructions in the error message. Click the link in the error to add the exception to your browser, and then     hit the "invoke" button again._   
   
   d. The expected response is a **200 OK** response code along with  the current weather data for 90210.
    
    ![](images/screenshot_test-1.png)    
    ![](images/screenshot_test-2.png)  


---

## Conclusion

In this tutorial, you saw how an existing REST service can be invoked through an API passthrough proxy. You started by checking the availability of the sample service through the web browser. Then you created an API proxy in API Connect, and linked the proxy to the sample service to be invoked. Finally, you tested this service with API Connect's internal testing tool.
