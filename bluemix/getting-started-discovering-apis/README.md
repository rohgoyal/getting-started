---

copyright:
  years: 2017
lastupdated: "2017-06-01"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Getting Started Discovering APIs
**Duration**: 30 mins  
**Skill level**: Beginner  


### Prerequisite
If you already have access to a developer portal, you may use this tutorial as a general guideline on how to navigate a developer portal. (Keep in mind that all developer portals have different skins. This tutorial will provide a general guideline on how to navigate one.) If not, you can [set up and configure a developer portal in Bluemix](https://github.com/ibm-apiconnect/getting-started/blob/master/bluemix/setup-config-customize-dev-portal/README.md) before proceeding with the tutorial on this page.


### Objective
In this tutorial you will learn how to consume the APIs in the API Connect Developer Portal. You will gain an understanding of how to explore products and APIs, view and test APIs, and subscribe to APIs. 
 

### Explore Products & APIs
In this section, you will explore the products and APIs in the developer portal.

1. In a browser, navigate to your **API Connect Developer Portal**.
![API Connect Developer Portal](images/1.1-developer-portal.png)

2. In the API Connect Developer Portal, select the **API Products** tab. 
![API Products](images/1.2-API-products.png)

3. Select one of the available **API products** to display the available APIs and Plans for the product.  
  ![Select Product](images/1.3-product.png)

4. Select an **API** to explore the details of the available APIs.  
  ![Products APIs](images/1.4-api.png)

5. In the details page of an API you can view the available operations along with their parameters and the responses returned. At the bottom of the page you can view the definitions used by the API.  
  ![API Details](images/1.5-details.png) 

6. In the right panel, you can view examples in different languages for how to invoke the requests and their responses. Select one of the examples, such as **Node**, to see an example in that language.  
  ![API Details](images/1.6-examples.png) 

---

### View and test the APIs
In this section, you will learn how to view and test the available APIs for a product. 

1. Navigate to the API details in the API Connect Developer portal as outlined above.  
  ![API Details](images/2.1-details.png) 

2. You can download and view the APIs Swagger yaml by selecting **Open API**.  
  ![Download Swagger yaml](images/2.2-swagger.png) 

3. Scroll down to one of the operations to view its details. You can also click on the operations link to jump to it on the page. 
![Operation](images/2.3-operation.png)

4. In the right panel under the examples, scroll down to the **Try this operation** section. Enter the parameters and select **Call operation**.  
  ![Try this operation](images/2.4-try-this-operation.png)

5. Scroll down to view the request and response of the operation call. A returned response of **200 OK** and the message body are displayed, indicating that the operation call was successful.  
  ![Operation response](images/2.5-operation-response.png)

---

### Subscribe to APIs
In this section, you will learn how to subscribe to APIs in the developer portal. Before you can subscribe to an API, you must login and create an application.

1. Select **Create an account**. 
![API Products](images/3.1-create-account.png)

2. Fill in the required fields and select **Create new account** at the bottom of the page. 
**Note:** Use a different email address than the one used to create your developer portal in the previous tutorial.
![API Products](images/3.2-create-new-account.png)

3. Once the developer account is created, log in to view the home page. You must have an app to subscribe to the APIs. Select **Apps** to go to the registered apps page.  
  ![API Products](images/3.3-login.png)

4. To register a new application, select **Create new App**.  
  ![Register new app](images/3.4-create-new-app.png)

5. Enter a *Title* and *Description* for your app and select **Submit**.  
  ![Submit new app](images/3.5-submit-new-app.png) 

6. Now that you have an App, you can subscribe to API Product plans. Select **available APIs** or **API Products** to browse the API Product plans.  
  ![API Details](images/3.6-api-products.png) 

7. Select the **API Product** you wish to subscribe to.  
  ![API Product](images/3.7-select-product.png) 

8. Select **Subscribe** to subscribe to the API Product Plan.  
  ![API Product Plan](images/3.8-subscribe-plan.png) 

9. Select the **app** you wish to subscribe to the product plan, then select **Subscribe**. 
  ![App Subscribe plan](images/3.9-subscribe-app-plan.png) 

10. Your application has successfully subscribed to the product plan. 
  ![App Subscribe Success](images/3.10-subscribe-success.png) 

### Conclusion
In this tutorial, you learned how to explore products and APIs, view and test APIs, and subscribe to APIs. 
