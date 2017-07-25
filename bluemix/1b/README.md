# Add a new API spec, and invoke an existing REST service with IBM Bluemix  
**Duration**: 15 mins  
**Skill level**: Beginner  

## Objective
This tutorial helps you get started quickly with **IBM API Connect** by illustrating how you can bring your existing API under management control. You'll start by creating a new OpenAPI spec, and then create a passthrough API proxy for an existing REST service.  

## Prerequisite
Before you begin, you will need to <a href="https://github.com/ibm-apiconnect/getting-started/tree/master/bluemix/0-prereq" target="blank">set up your API Connect instance</a>.  

---


## Explore the sample app and test the target endpoints
A sample _weather provider_ app has been created for this tutorial. 
1. To explore the app, go to http://gettingstartedweatherapp.mybluemix.net/.  
2. Enter a valid 5-digit U.S. zipcode to get the _**current weather**_ and _**today's forecast**_.  
  ![](images/explore-weatherapp-1.png)

3. The above sample weather app was built using APIs that provide the weather data. The endpoint to get the **current** weather data is _**https:// myweatherprovider<span></span>.mybluemix.net/current?zipcode={zipcode}**_. Test it out by visiting https://myweatherprovider.mybluemix.net/current?zipcode=90210.  
  ![](images/explore-weatherapp-2.png)

4. Similarly, the Endpoint to get **today's** forecast data is _**https:// myweatherprovider<span></span>.mybluemix.net/today?zipcode={zipcode}**_. Test it out by going to https://myweatherprovider.mybluemix.net/today?zipcode=90210.  
  ![](images/explore-weatherapp-3.png)


---

## Add a new OpenAPI spec to create a REST API proxy  
1. Log in to IBM Bluemix: https://new-console.ng.bluemix.net/login.
2. Once logged in to Bluemix, scroll down to **All Services**, and click on **API Connect**. 
3. Click on **API Connect** to launch the API Connect service.  
  ![](images/bluemix-launch-apic.png)    
  
4. In the API Connect interface, make sure the navigation panel on the left side is open. If not, click **>>** to open it.  
5. Click on **Drafts** in the navigation panel.   
6. Go to the **APIs** tab
7. In the **APIs** tab, click **Add**

8. In the dropdown menu, click **New API**.    
  ![](images/create-new-1.png)  
  
9. In the **New API** window, enter ```Weather Provider API``` for the title.
_The Name and Base Path are auto-populated_.  
  ![](images/bluemix-add-new-api.png)   
  
10. Click **Create API** to complete the wizard.  Once you've created your OpenAPI spec, you are taken to the **Design** view.  
11. In the **Design** view, scroll to the **Host** panel. 
12. Enter ```$(catalog.host)``` as the value, if the field is not automatically filled in.  
13. Scroll to the **Security** tab, and click the delete icon to remove the `clientIDHeader (API Key)` that was auto-generated.  
> _You will cover security with API Keys in the next tutorial._  

14. In the side navigation panel:  
    a. scroll down to the **Paths** panel.   
    b. Create a new path by clicking **+**.   
    c. Name the new path "**/current**".  
    d. In the same *Paths* panel, click on **GET /current** to open that section.    
    e. In the **GET /current** section, add a new **Parameter**. As you noticed while exploring the ![sample app](http://gettingstartedweatherapp.mybluemix.net/), the weather service requires zipcode as a parameter.  
       - Name: zipcode  
       - Located in: Query  
       - Required: Yes (check mark)  
       - Type: string   
      ![](images/path-current-1.png)   
        

15. With your query parameters defined in the previous step, you need to now define the response object that is returned when you incoke the weather API. To do so, in the navigation panel:  
    a. Scroll down to the **Definitions** panel   
    b. Add a new definition  
    c. Name the new definition _Current_  
    d. Set the Type to _Object_   
    e. Add new properties for the **Current** definition.    
       - Name: zip         /  Type: string   
       - Name: temperature /  Type: integer   
       - Name: humidity    /  Type: integer   
       - Name: city        /  Type: string   
       - Name: state       /  Type: string   
    ![](images/definition-current-1.png)   
     

16. In the previous step, you defined the response object. Next you'll need to ensure the response object is associated with the **get /current** path.  
    In the left side-navigation panel, scroll back up to the **Paths** panel.  
    a. Open the **GET /current** operation, and scroll to the **Responses** section.  
    b. Change the schema of the 200OK response from "object" to "**Current**".  
    c. Save your API by clicking on the save icon on the top right corner of the designer. An "API Saved" confirmation notification appears momentarily.  
    > _The path and operation you created was to get the current weather data. Next, you'll need to create a similar path and operation to get today's weather data._  

17. Similar to how you created the **/current** path in the previous steps, create a new path: **/today**.
18. Add a new Parameter under the **GET /today** operation.
      - Parameter Name: zipcode
      - Located in: Query
      - Required: Yes (check mark)
      - Type: string  

19. Create a new definition: **Today**.
20. Add new properties for the **Today** definition.
      - Name: zip / Type: string
      - Name: hi / Type: integer
      - Name: lo / Type: integer
      - Name: nightHumidity / Type: integer
      - Name: dayHumidity / Type: integer
      - Name: city / Type: string
      - Name: state / Type: string
21. Update the response schema in the **GET /today** section to "Today".
22. Save your API.

23. Switch over to the **Assemble** tab. You've got two operations so far: **GET /current** and **GET /today**. To ensure the correct target endpoint is invoked, you'll need to create some logic that will execute conditional on the operation that's being called. Let's use the **Operation Switch** logic construct to do this.  
    a. Delete the **invoke** policy that may already be added to the _canvas_.  
    b. From the palette, drag the **Operation Switch** and drop it on the canvas.  
       - To **case 0**, assign the **get /current** operation.
       - Add a new Case: **case 1**.
       - Assign the **get /today** operation to **case 1**.
       ![](images/assemble-1.png)  
        _The **Operation Switch** provides a decision point. Based on the verb/path pair, the appropriate operation needs to be invoked._   
          
    c. Drag the **invoke** policy from the palette and drop it on the canvas. _The invoke action is used to call an existing service from within an operation_.  
       - Drop an invoke action in the **/get current** path, and one in the **/get today** path.   
       - Select the **invoke** policy in the **/get current** path, and update its title to "**invoke-current**".  
       - Update the URL field with https://myweatherprovider.mybluemix.net/current?zipcode=$(request.parameters.zipcode).  
       - Select the **invoke** policy in the **/get today** path, and update its title to "**invoke-today**".  
       - Update the URL field with https://myweatherprovider.mybluemix.net/today?zipcode=$(request.parameters.zipcode).  
       ![](images/assemble-2.png)  

24. Save your API.

---

### Test your API proxy
1. In the **Assemble** tab, click on **More Actions** then click **Generate a default product**.  
   ![](/bluemix/1a/images/generate-default-product-1.png) 

2. Accept the default options in the **New Product** dialog box, and click **Create Product**. The **Weather Provider API product** is created and published to the Sandbox catalog. A message indicating successful product generation is displayed.  
  ![](/bluemix/1a/images/generate-default-product-2.png)  
  
  ![](/bluemix/1a/images/generate-default-product-3.png) 

  > _In API Connect, **Products** provide a way to group APIs that are intended for a particular use. Products are published to a **Catalog**. [Reference: API Connect glossary]_

3. On the Assemble tab, click ► to test your API proxy's target invocation.  
   a. Choose the **get /current** operation.  
   b. Zipcode is a required parameter for this operation, so enter a valid U.S. zip (for example, 90210).  
   c. Click **invoke**, and verify the response.  
  > _If you run into a CORS error, follow the instructions in the error message. Click the link in the error to add the exception to your browser, and then hit the "invoke" button again._   
  
   d. The expected response is a **200 OK** response code along with  the current weather data for 90210.  
    ![](images/test-invoke-1.png) 
    ![](images/test-invoke-2.png) 
    ![](images/test-invoke-3.png) 


---


### Conclusion
In this tutorial, you saw how an existing REST service can be invoked through an API passthrough proxy. You started by checking the availability of the sample service through the web browser. Then you created a new OpenAPI spec in API Connect, and linked it to the sample service to be invoked. You packaged your API into a product, published the product to catalog, and tested the proxy.
