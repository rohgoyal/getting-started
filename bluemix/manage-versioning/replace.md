---
 
copyright:
years: 2017
lastupdated: "2017-08-04"
 
---
# Replacing an API Product
**Duration**: 15 mins  
**Skill level**: Beginner  

[Prerequisites](https://github.com/ibm-apiconnect/getting-started/blob/master/bluemix/0-prereq/README.md)

Complete the Proxy REST API tutorial.

---
### Objective
In this tutorial, you will update an existing API product by replacing it with a newer one.

When an API product is **replaced**, the changes take effect immediately and all application subscriptions are updated automatically.  


---
### Replacing an API Product
1. Log in to IBM Bluemix: https://new-console.ng.bluemix.net/login.

2. In the Bluemix **Dashboard**, launch the API Connect service.
![](images/Bluemix.png)

3. In API Manager, if you have not previously pinned the UI navigation pane then click the **Navigate to** icon ![](images/navigate-to.png).  The API Manager UI navigation pane opens. To pin the UI Navigation pane, click the **Pin menu** icon ![](images/pinned.png).

4. Click **Drafts** > **APIs**.

5. In the APIs panel, click **Weather Provider API** open the REST proxy API.  


![](images/rep-api-list.png)


6. Change the **Version** to 2.0.0.  

7. Click the disk icon to save the API changes.  


![](images/rep-change-version.png)


8. Click **All APIs**.  


![](images/rep-all-apis.png)


9. Click **Products**.  


![](images/rep-api-list-2.png)


10.	Click **Weather Provider API Product**.  


![](images/rep-draft-prod-list.png)



11.	Change the **Version** to 2.0.0. Enter ``Updated API`` in the **Description** field.  Click the disk icon to save the changes.  


![](images/rep-update-prod.png)


12.	Click **Stage**.  


![](images/rep-stage-prod-2.png)


13.	Click **>>** to open the navigation menu, then select Dashboard.  


![](images/rep-dashboard.png)


14.	Click **Sandbox**.  


15.	Click the three vertical dots on the **Weather Provider API Product 2.0.0 Staged** line.  


![](images/rep-dash-prod-list-2.png)


16.	Select **Replace an existing product**.  


![](images/rep-replace-prod.png)


17.	Select **Weather Provider API Product 1.0.0** in the list of products presented.  Click **Next**.  


![](images/rep-replace-dialog.png)

18.	Select **Default plan**.  Click **Replace**.  


![](images/rep-replace-dialog-2.png)

As a result of this replacement, the Weather Provider API Product 1.0.0 is retired, and the Weather Provider API Product 2.0.0
 is published.  

 
 ![](images/rep-prod-retired.png) 
 

### What you did in this tutorial
In this tutorial, you completed the following activities:
1. Updated an API Product
2. Replaced an existing API Product with an updated API Product

---
