---
layout: default
title: PriceOverride
nav_order: 17
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### PriceOverride 

This message is called to do a price override on the specified line
item. The request includes the line number and a signed decimal value of
the new price. Optionally, a reason code may be included in the request,
if not included the default is 1. The response will include updated
totals and items list.

**Uri**: /baskets/{id}/items/{linenumber}/prices

**Http Verb**: POST

**Request body**:
```csharp
public class ManualUnitPrice
{
/// <summary>
/// New unit price
/// </summary>

public decimal UnitPrice;
/// <summary>
/// Optional reason code
/// </summary>

public int? ReasonCode;
}
```
**Response body**:
```csharp
public class ItemUpdatesResponse
{
/// <summary>
/// Existing items whose net selling price changes as a result (i.e.prorated taxes
/// discounts changed). First item will be the item whose unit price changed
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
Example:
```json
{"ChangedItems":[{"ItemCode":"0000126","ScanCode":"0000126",
"Description":"Tournament
yo-yo","Quantity":1.0,"UnitPrice":8.0,"ExtendedPrice":8.0,
"DiscountAmount":-0.80,"TaxAmount":0.24,"UnitOfMessure":1,
"VoidCode":0,"IsItemAuthorizationRequired":false,"AccountToken":null,
"ProratedDiscounts":[{"Description":"Manual
Item
Percent","Amount":-0.80,"LineNumber":10}],"Proratedtaxes":
[{"Description":"NC-State
Tax","Amount":0.07,"IsVAT":false,"AuthorityId":37000,"Id":-1,"LineNumber":11},
{"Description":"DurhamCo.
Tax","Amount":0.17,"IsVAT":false,"AuthorityId":37063,"Id":1,
"LineNumber":5}],"LineNumber":7}],"Taxes":[{"Description":"DurhamCo.
Tax","Amount":0.17,"IsVAT":false,"AuthorityId":37063,"Id":1,"LineNumber":5},
{"Description":"NC-State
Tax","Amount":0.07,"IsVAT":false,"AuthorityId":37000,"Id":-1,"LineNumber":11}],
"Discounts":[{"Description":"Benign
coupon for
points","Amount":-0.010000,"LineNumber":9},{"Description":"Manual
Item
Percent","Amount":-0.80,"LineNumber":10}],"SubTotal":8.0,"TaxTotal":0.24,
"DiscountTotal":-0.80}
```