# Add a new API spec, and proxy an existing REST service
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

#### Import the sample app's OpenAPI spec to create a REST API proxy
- Log in to IBM Bluemix: https://new-console.ng.bluemix.net/login
- In the Bluemix navigation panel (left hand), select **Services** and click **Dashboard**
- Launch the API Connect service
- In API Connect, click on **Drafts > APIs> Import API from a file or URL**
- 

~~screenshots~~
