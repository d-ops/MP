---
layout: default
title: AddCustomer
nav_order: 9
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# AddCustomer
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
---
This message is sent to lookup a customer in the customer loyalty system
(SAP) and add to the current basket. The customer must exist to be
assigned to the device. Only one of CustomerNumber or PhoneNumber will
be supplied.

## Uri
/baskets/{id}/customers

## Http Verb
POST

## Request Body

```csharp
public class CustomerDetails
{
/// <summary>
/// Customer number
/// </summary>

public string CustomerId;
/// <summary>
/// True if an order customer
/// </summary>

public bool IsOrderCustomer;
}
```
## Response Body

```csharp
/// <summary>
/// Response to add customer
/// </summary>

public class AddCustomerResponse
{
/// <summary>
/// Details about the customer
/// </summary>
[DataMember]

public CustomerInformation Customer;
/// <summary>
/// Existing items whose net selling price changes as a result (i.e.
prorated taxes / discounts changed)
/// </summary>

public ItemDetails[] ChangedItems;
/// <summary>
/// Tax details
/// </summary>

public TaxDetails[] Taxes;
/// <summary>
/// Discount details
/// </summary>

public DiscountDetails[] Discounts;
/// <summary>
/// Total extended amount of items
/// </summary>

public decimal SubTotal;
/// <summary>
/// Total tax amount
/// </summary>

public decimal TaxTotal;
/// <summary>
/// Total discount amount
/// </summary>
public decimal DiscountTotal;
}
```
## Example
```json
[{"CustomerNumber":"6100000011","LoyaltyNumber":"4100000000123","CallingCode":null,"AreaCode":"415",
"PhoneNumber":"4152221111","CustomerName":"JohnHarrison",
"Address":"75 Geary StrnApt#165","City":"SanFrancisco",
"State":"CA","PostCode":"94103",
"Country":"USA","EmailAddress":"john@homemail.com"}])
```