# Secure your API with a client ID and secret

 
Duration: 10 mins

Skill level: Beginner
 
 
## Objective

This tutorial is to guide you through securing your API with the keys so that any application calling your API would need to supply the Client ID and Client Secret keys. In this tutorial, we will modify the API that we previously worked with in Part 1.

## Prerequisites

Completed Part 1: Import your API and proxy an existing service


## Set the identification mechanism of your API

1. Go back to your API's Design view

2. Scroll over to Security Definitions

3. Add two new API keys: 

4. Name: Client ID;  Parameter name: X-IBM-Client-ID

5. Name: Client Secret;  Parameter name: X-IBM-Client-Secret
![](https://ibm.box.com/shared/static/uyv23n7zl4itu091knjwfczhqjvocmbp.jpg)

6. For both new keys, ensure that the "Located In" field is set to "Header"

7. Scroll down to the Security section, and add a new security option

8. Select the newly created Client ID and Client Secret keys

9. Save your API, and switch over to the Assemble tab
![](https://ibm.box.com/shared/static/oogendl4fe9rnwbe04luey9gwgx9lkdk.jpg)

> < screenshots > create from screen recording  
> < screen recording https://ibm.box.com/s/t8btx2uwe68cmhhayyrya9hloybnzi14 > only for internal use

  

##Test the changes made to your API##

1. In the Assemble tab, click the ► button to test your changes

2. In the Test / Setup, choose to Republish the product to pickup the changes. This option updates your API product, and also publishes it to the catalog

3. Scroll down in the Test panel, and notice that the Client ID and Client Secret values have already been populated. These are test values that are generated for your sandbox, and represent the keys of the application that will be using your API. [ Note: The Client ID and Client Secret keys can also be found under  Dashboard > Catalog > Settings > Endpoints ]
![](https://ibm.box.com/shared/static/lleen2lw1vo4bgdwobumk2s5bznp0izw.jpg)

4. Scroll further down, and click invoke

5. You should get a 200 OK response, along with the message body returning the branch details
![](https://ibm.box.com/shared/static/tr85ot2eynvgye7f3jg6btvcwrsr14tk.jpg)

6. Now scroll back up to the Client ID field, and replace the value with a random one

7. Rerun the test by clicking invoke

8. You'll see a 401 Unauthorized response, along with details: "Client ID not registered"
![](https://ibm.box.com/shared/static/53njkbxo6kllqdh2ukdg0v7rjtfjn0nn.jpg)




##Call your API using the Client ID and Client Secret (optional)##

The security settings can also be tested using the Explore tool that explicitly calls the proxy endpoint, and passes the Client ID and Client Secret keys as header values.

1. Click Explore > Sandbox

2. Click on the GET /branches operation from the list

3. In the right-hand column, use the Call Operation button to rerun the test


