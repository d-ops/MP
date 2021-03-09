---
layout: default
title: LookupItem
nav_order: 11
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### LookupItem 

This message is sent to get item details. It's used for price check
functionality or to get details like not on file, not authorized for
sale, age restricted, quantity / weight required flags prior to actually
selling the item.

This method can also be used to lookup customer loyalty cards and store
coupons if the client application cannot determine the item type from a
scan code or manually entered code. Internally the server service will
determine the item type by code length or scan code prefix. Note if it
is a customer id then it will not lookup the customer in the CRM system
-- that is done by calling LookupCustomer.

**Uri**: /items/{itemcode}

**Http Verb**: GET

**Response Body**:
```csharp
/// <summary>
/// Sale item within basket
/// </summary>

public class ItemInformation
{
/// <summary>
/// Item code
/// </summary>

public string ItemCode;
/// <summary>
/// Scan code
/// </summary>

public string ScanCode;
/// <summary>
/// Item description
/// </summary>

public string Description;
/// <summary>
/// Unit price
/// </summary>

public decimal UnitPrice;
/// <summary>
/// Unit of measure id
/// </summary>

public int UnitOfMessure;
/// <summary>
/// True if item requires authorization for sale ( gift card sale etc )
/// </summary>

[DataMember]

public bool IsItemAuthorizationRequiredForSale;
/// <summary>
/// True if item requires authorization for refund ( gift card sale etc)
/// </summary>

[DataMember]

public bool IsItemAuthorizationRequiredForReturn;

/// <summary>
/// True if the weight is required
/// </summary>

public bool WeightRequired;
/// <summary>
/// True if the item quantity is required
/// </summary>

public bool QuantityRequired;
/// <summary>
/// True if the item is a price required item
/// </summary>

public bool PriceRequired;
/// <summary>
/// True if the item is not on file
/// </summary>

public bool NotOnFile;
/// <summary>
/// True if the item is a commissioned item
/// </summary>

public bool CommissionedItem;
/// <summary>
/// True if a serial number is required
/// </summary>

public bool SerialNumberRequired;
/// <summary>
/// True if the item cannot be sold at this time
/// </summary>

public bool NotForSale;
/// <summary>
/// True if the item is a store coupon
/// </summary>

public bool IsStoreCoupon;
/// <summary>
/// True if the item is a customer number
/// </summary>

public bool IsCustomerID;
}
```
Example:
```json
{"ItemCode":"0000126","ScanCode":"0000126","Description":"Tournament
yo-yo","UnitPrice":9.990000,"UnitOfMessure":1,
"IsItemAuthorizationRequiredForSale":false,
"IsItemAuthorizationRequiredForReturn":false,
"WeightRequired":false,"QuantityRequired":false,
"PriceRequired":false,"NotOnFile":false,
"CommissionedItem":false,"SerialNumberRequired":false,
"NotForSale":false,"IsStoreCoupon":false,"IsCustomerID":false}
```