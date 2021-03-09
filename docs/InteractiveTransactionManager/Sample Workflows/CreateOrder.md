---
layout: default
title: Create Order
nav_order: 3
parent: Sample Workflow
grand_parent: Interactive Transaction Manager
has_children: true
---

### Create Order

Initial Workflow is completed

mPOS sends LookupCustomer to find customer by available search criteria.

ITSREST sends array of CustomerInformation records for each found customer. This step can be skipped if the customer id / loyalty id is known.

mPOS sends AddCustomer with found customer id / loyalty id to ITS REST API.

ITS REST sends AddCustomerResponse.

mPOS prompts for delivery information ( home address / current store or nearby store). Note if a nearby store is used then LookupNearbyStores method may be called by the mPOS to find details of the nearby stores.

mPOS sends CreateOrder to ITS REST API.

ITS REST sends OrderDetails response.

mPOS sends LookupInventoryItem to ITS REST API to find details by location where the item is available for order.

ITS REST sends array of InventoryItemDetails records for the found items.

mPOS sends AddOrderItem including details of the location from where the item will be ordered.

ITS REST sends OrderDetails response.

If a payment is required then Operator swipes Credit card

mPOS sends ValidateTender message to ITS REST API.

If the validation is successful then mPOS sends authorize tender message to authorizer for the payment amount

mPOS sends AddAuthorizedTender message to ITS REST API with information from authorizer

ITS REST sends AddAuthorizedTenderResponse

If the payment above was a partial payment then the balance is paid using a future payment tender – mPOS sends AddAuthorizedTender with the future payment tender code (105 in sample data).

ITS REST sends AddAuthorizedTenderResponse

mPOS sends EndTransaction message to ITS REST API.

ITS REST sends EndTransactionResponse
