---
layout: default
title: GetBasket
nav_order: 6
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### GetBasket 

This message is sent to get details about the current basket. It should
be called after any unexpected error response to a basket update command
so that the client and ITM can resynchronize.

**Uri**: /baskets/{id}

**Http Verb**: GET

**Response body data**:
```csharp
/// <summary>
/// Details about a basket
/// </summary>

public class BasketDetails : BasketIdentifier
{
/// <summary>
/// Basket line items
/// </summary>

public ItemDetails[] Items;
/// <summary>
/// Tax details
/// </summary>

public TaxDetails[] Taxes;
/// <summary>
/// Discount details
/// </summary>

public DiscountDetails[] Discounts;
/// <summary>
/// Tender details
/// </summary>

public TenderDetails[] Tenders;
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
/// <summary>
/// Total tendered amount
/// </summary>

public decimal TenderTotal;
}
```
Example:
```json
{"Items":[{"ItemCode":"0000126","ScanCode":"0000126","Description":"Tournament
yo-yo","Quantity":1.0,"UnitPrice":9.990000,"ExtendedPrice":9.99,"DiscountAmount":0.0,"TaxAmount":0.71,"UnitOfMessure":1,"VoidCode":0,"IsItemAuthorizationRequired":false,"AccountToken":null,"ProratedDiscounts":null,"Proratedtaxes":[{"Description":"NC-State
Tax","Amount":0.48,"IsVAT":false,"AuthorityId":37000,"Id":1,"LineNumber":1},{"Description":"Durham
Co.
Tax","Amount":0.23,"IsVAT":false,"AuthorityId":37063,"Id":1,"LineNumber":5}],"LineNumber":7}],
"Taxes":[{"Description":"NC-State
Tax","Amount":0.48,"IsVAT":false,"AuthorityId":37000,"Id":1,"LineNumber":1},{"Description":"Durham
Co.
Tax","Amount":0.23,"IsVAT":false,"AuthorityId":37063,"Id":1,"LineNumber":5}],
"Discounts":[{"Description":"Benign coupon for
points","Amount":-0.010000,"LineNumber":9}],
"Tenders":[],
"SubTotal":9.99,
"TaxTotal":0.71,
"DiscountTotal":0.0,
"TenderTotal":0.0,
"Id":"a206f48b-9fba-4aaa-b723-2b95d577211a",
"TransactionNumber":2}
```