# Add a new API spec and invoke an existing REST service
Duration: 5 mins  
Skill level: Beginner  


#### Objective
This tutorial is to help you get started quickly with **API Connect**. We'll start by creating a new OpenAPI spec, and then proxy existing REST services used by the sample weather app.

---


#### Explore the sample app, and test the target endpoints
A sample _weather provider_ app has been created for this tutorial
- Explore this app here: http://gettingstartedweatherapp.mybluemix.net/
- Enter a valid 5-digit US zipcode to get the _**current weather**_ and _**today's forecast**_  
![](images/explore-weatherapp-1.png)

  - Endpoint to get the **current** weather data is:     _**https:// myweatherprovider<span></span>.mybluemix.net/current?zipcode={zipcode}**_
  - Test it out by clicking: https://myweatherprovider.mybluemix.net/current?zipcode=90210  
  ![](images/explore-weatherapp-2.png)

  - Endpoint to get **today's** forecast data is:  
   _**https:// myweatherprovider<span></span>.mybluemix.net/today?zipcode={zipcode}**_
  - Test it out by clicking: https://myweatherprovider.mybluemix.net/today?zipcode=90210  
  ![](images/explore-weatherapp-3.png)


---

#### Add a new OpenAPI spec and invoke an existing REST service
- Log in to IBM Bluemix: https://new-console.ng.bluemix.net/login
- In the Bluemix navigation panel (left hand), select **Services** and click **Dashboard**
- Launch the API Connect service
- In API Connect, go to **Drafts > APIs**
- In the New API popup, enter the title "Weather Provider API"  
_The Name and Base Path are auto-populated_  
- Click **Create API** to complete the wizard  

##! screenshot  


- Once your API is created, you are taken to the **Design** tab
- Scroll down to the **Host** panel, and note the value that's filled in: ```$(catalog.host)```
- In the **Base Path** panel, note the auto-populated value: ```/weather-provider-api```
- Your API's target URL will be created from these values

- Scroll down to the **Security** tab, and delete the "clientIDHeader (API Key)" that has been been auto-generated  
_We'll visit security with API Keys in the next tutorial_  


- Scroll down to the **Paths** panel
  - Create a new path, and name it "**/current**"
  - In the same **Paths** panel, click on the **GET /current** section
  - Add a new Parameter
    - Name: zipcode
    - Located in: Query
    - Required: Yes (check mark)
    - Type: string
  - Save your API, and scroll down to the **Definitions** panel



- In the **Definitions** panel,
  - add a new definition
    - Name: Current  /  Type: Object
    - Add new properties for the **Current** definition
    - Name: zip         /  Type: string
    - Name: temperature /  Type: integer
    - Name: humidity    /  Type: integer
    - Name: city        /  Type: string
    - Name: state       /  Type: string
  - Save your API
 ##! screenshot

  - Scroll back up to the **Paths** panel
    - Open the **GET /current** operation, and scroll to the **Responses** section
    - Change the schema of the 200OK response from "object" to "**Current**"
    - Save your API
    - The path and operation you created was to get the current weather data. Next you'll need to create the same to get today's weather data.  




  - Create a new path: **/today**
    - Add a new Parameter under the **GET /today** operation
      - Parameter Name: zipcode
      - Located in: Query
      - Required: Yes (check mark)
      - Type: string  

##! screenshot
  - Create a new definition: **Today**
    - Add new properties for the **Today** definition
    - Name: zip / Type: string
    - Name: hi / Type: integer
    - Name: lo / Type: integer
    - Name: nightHumidity / Type: integer
    - Name: dayHumidity / Type: integer
    - Name: city / Type: string
    - Name: state / Type: string
  - Update the response schema in the **GET /today** section to "Today"
  - Save your API

##! screenshot


- Switch over to the **Assemble** tab
  -  You've got two operations so far: **GET /current** and **GET /today**. To ensure the right target endpoint is invoked, you'll need to create some logic that will execute conditional on the operation that's being called. Let's use the **Operation Switch** logic construct to do this
  - First, delete the **invoke** policy that may already be added to the _canvas_
  - Then, from the _palette_, drag the **Operation Switch** and drop it on the canvas
    - To **case 0**, assign the **get /current** operation
    - Add a new Case -- **case 1**
    - To **case 1**, assign the **get /today** operation
  - The **Operation Switch**  provides a decision point -- based on the verb/path pair, the appropriate operation needs to be invoked.
  - Drag the **invoke** policy from the _palette_ and drop it on the canvas; drop one in the **/get current** path, and one in the **/get today** path
    - Select the **invoke** policy in the **/get current** path, and update its title to "**invoke-current**"
    - Update the URL field with https://myweatherprovider.mybluemix.net/current?zipcode={zipcode}  
    - Select the **invoke** policy in the **/get today** path, and update its title to "**invoke-today**"
    - Update the URL field with https://myweatherprovider.mybluemix.net/today?zipcode={zipcode}  
- Save your API

##! screenshot

---

#### Test your API proxy
- In the **Assemble** tab, click **More Actions > Generate a default product**
  - Accept the default options in the **New Product** dialog popup, and click **Create Product**
  - The **Weather Provider API product** is created and published to the Sandbox catalog
  - _In API Connect, **Products** provide a mechanism to  group APIs that intended for a particular use. Products are published to a **Catalog**.  [Reference: API Connect glossary]_
  - Save and click ► to test the API service
  - Choose the newly created default product, and the **get /current** operation
  - Zipcode is a required parameter for this operation, so enter a valid US zip (e.g. 90210)
  - Click **invoke**, and verify that you see:
    - 200 OK response
    - current weather data for 90210
##! screenshot
