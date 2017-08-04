---
 
copyright:
years: 2017
lastupdated: "2017-08-04"
 
---
# Managing API and Product versions

Once an API and the product that contains it are published, API providers typically want or need to update those products and APIs.  Updating an API product can happen in different ways.  

- Replace the old with the new, automatically updating all subscriptions
- Supercede the old with the new, manually updating subscriptions on a per app basis

Once replaced, an API product can then be taken out of service and removed using a series of steps.

- Deprecate the API product.  This prevents any new subscriptions to the API but does not prohibit usage.
- Retire the API product.  This prevents any use of the API but does not remove it.
- Archive the API product.  This removes the API from use but does not delete it completely; it can be reinstated..
- Delete the API product.  The API product is gone completely and cannot be retrieved.

In this series of tutorials, you will move API products through all of these states.  The tutorials shouild be done in the following order.

- [Replace an API product](replace.md)
- [Supercede an API product](supercede.md)
- [Archive and Delete an API product](delete.md)


---
