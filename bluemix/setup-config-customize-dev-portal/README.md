---

copyright:
  years: 2017
lastupdated: "2017-05-16"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Set Up and Configure Your Developer Portal
**Duration**: 30 mins  
**Skill level**: Beginner  

### Prerequisites
Before you begin, you will need to [import your API spec and proxy an existing REST service](https://github.com/ibm-apiconnect/getting-started/blob/master/bluemix/1a/README.md).

### Objective
This tutorial will help you quickly get started with configuring your **API Connect Developer Portal**. 

---

### Create your developer portal
In this section, you will create a developer portal for a catalog.

Catalogs are an IBM term for different enviornments. For example, you would create different catalogs for your testing, staging, and production enviornments. You should have a catalog called Sandbox. Feel free to use this catalog to create your developer portal, or create a new one and name it whatever you want.

1. In your Bluemix dashboard, select your **API Connect** service to launch the API Connect dashboard.
![API Connect Service](images/1.1-Bluemix-Dashboard.png)

2. In the API Connect dashboard, select the catalog for which you want to create a developer portal. For example, **Sandbox**.
![Catalog](images/1.2-APIC-Dashboard.png)

3. In the catalog, select the **Settings** tab.  
  ![Catalog Settings](images/1.3-catalog-settings.png)

4. In the Settings tab, select **Portal**.  
  ![Portal configuration](images/1.4-catalog-portal.png)

5. On the Portal Configuration page, select **IBM Developer Portal** from the Select Portal dropdown. 
  ![IBM Developer Portal](images/1.5-IBM-developer-portal.png) 

6. Take note of your **Portal URL**, then save your changes.  
  ![Save settings](images/1.6-save-settings.png)
  
7. As noted in the dialog box, it typically takes a few minutes to create your developer portal. You will receive an email when it has finished. Select **OK** to acknowledge the dialog message.  
  ![OK](images/1.7-OK.png)

---

### Explore your developer portal
In this section, you will get acquainted with the developer portal you created i the previous steps.

1. After you have configured the developer portal for your catalog, you will receive an email with a link to a one-time login. Select the link to launch the developer portal.

2. Select **Login** to log in to the developer portal. 
![Login](images/2.2-login.png)

3. Enter a new password and click **Save**.  
  ![Enter new password](images/2.3-password.png)

4. Now that you've set your password, let's explore the developer portal. Select **Home** at the top of the page.  
  ![Home menu](images/2.4-pwsaved.png)

5. The Home page is the welcome page to your developer portal. You can customize this page to suit your needs. When you've finished reviewing the home page, select **Getting started**.   
  ![Getting started menu](images/2.5-home.png) 

6. The Getting started page is used to instruct developers how to get started using your developer portal. When you've finished reviewing the page, select **API Products**.
  ![API Products Menu](images/2.6-getting-started.png)

7. The API Products page is used by developers to explore and subscribe to the APIs that are available on your portal. When you've finished reviewing the page, select one of the products.  
  ![API Products](images/2.7-api-products.png)

8. The Product page for an API shows the available plans for the product and enables developers to subscribe to and view the API details. When you've finished reviewing the page, select **Apps**.  
  ![API Product Plans](images/2.8-api-plan.png)

9. The Apps page displays the applications that are using your APIs. When you've finished reviewing the page, select **Blogs**.  
  ![API Product Apps](images/2.9-apps.png)

10. The Blogs page is where you can create and display blog posts about your APIs. When you've finished reviewing the page select **Forums**.  
  ![Blogs](images/2.10-blogs.png)
  
11. The Forums page is where developers can have discussions and post questions about your APIs. When you've finished reviewing the page select **Support**.  
  ![Forums](images/2.11-forums.png)
  
12. The Support page is where you can direct developers on how they can receive support on your APIs. For example, you can refer them to your forums and FAQs. You can also provide a link that allows them to open a support ticket if needed.  
  ![Support](images/2.12-support.png)

### Conclusion
In this tutorial, you learned how to set up and configure your API Connect Developer Portal. 


  
