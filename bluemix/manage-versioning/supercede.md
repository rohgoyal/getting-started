---
 
copyright:
years: 2017
lastupdated: "2017-08-01"
 
---
# Updating and Removing API Products
**Duration**: 15 mins  
**Skill level**: Intermediate  

[Prerequisites](https://github.com/ibm-apiconnect/getting-started/blob/master/bluemix/0-prereq/README.md)

Complete the Superceding an Existing API tutorial.

---
### Objective
In this tutorial, you will retire, archive and delete APIs.

---
### Deleting an API Product
1. Log in to IBM Bluemix: https://new-console.ng.bluemix.net/login.

2. In the Bluemix **Dashboard**, launch the API Connect service.
![](images/Bluemix.png)

3. In API Manager, if you have not previously pinned the UI navigation pane then click the **Navigate to** icon ![](images/navigate-to.png).  The API Manager UI navigation pane opens. To pin the UI Navigation pane, click the **Pin menu** icon ![](images/pinned.png).

4. Click **Sandbox** to open the Sandbox catalog.
![](images/del-sandbox-list.png)

5. Click the three vertical dots on the line listing **Weather Provider API 1.0.0**.
![](images/del-prod-list1.png)

6. Change the **Version** to 3.0.0.

7. Click the disk icon to save the API changes.
![](images/sup-change-version.png)

8. Click **All APIs**.

9. Click **Products**.
![](images/sup-prods.png)

10.	Click **Weather Provider API Product 2.0.0**.
![](images/sup-draft-prod-list.png)

11.	Change the **Version** to 3.0.0. Click the disk icon to save the changes. Click **Stage**.
![](images/sup-change-prod-vers-3.png)

12.	Click **>>** to open the navigation menu, then select Dashboard.
![](images/rep-dashboard.png)

13.	Click **Sandbox**.

14.	Click **Community**.
![](images/sup-sand-dash.png)

15.	Click **Subscriptions**.  
![](images/sup-comm-orgs.png)

16.	Note the application subscriptions to Weather Provider API Product 2.0.0.  Click **Products**.
![](images/sup-scriptions-200.png)

17.	Click the three vertical dots on the **Weather Provider API Product 3.0.0 Staged** line.
![](images/sup-stage-prod-3.png)

18.	Select **Supercede an existing product**.
![](images/sup-super-prod.png)

19.	Select **Weather Provider API Product 2.0.0** in the list of products presented.  Click **Next**.
![](images/sup-super-dialog-1.png)

20.	Select **Default plan**.  Click **Supercede**.
![](images/sup-super-dialog-2.png)

As a result of this replacement, the Weather Provider API Product 2.0.0 is deprecated, and the Weather Provider API Product 3.0.0 is published.
![](images/sup-dash-prods-3.png) 
 
21.	Click **Supercede >> Subscriptions**.
![](images/sup-scriptions-200.png)
 
22.	Click the three vertical dots on the **Weather Provider API Product 2.0.0** line.  Select **Manage**.
![](images/sup-dots-manage.png) 

23.	Select **Default plan** under Weather Provider API Product 3.0.0 .  Click **Migrate**.
![](images/sup-migrate-dialog.png)

As a result of this migration, the Weather Provider API Product 2.0.0 is migrated to Weather Provider API Product 3.0.0.
![](images/sup-migrated.png) 
 
 
### What you did in this tutorial
In this tutorial, you completed the following activities:
1. Updated an API Product
2. Superceded an existing API Product with an updated API Product
3. Migrated the subscription to the existing API product to the updated API product.

---
