---
layout: default
title: LineItemDiscount
nav_order: 14
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### LineItemDiscount 

This message is called to perform a percentage or amount off line item
discount. Optionally the request can include a reason code. A list of
items and updated totals information is returned in the response.

**Uri**: /baskets/{id}/items/{linenumber}/discounts

**Http Verb**: POST

**Request Body**:
```csharp
public class ManualDiscount
{
/// <summary>
/// Discount value - amount or percentage amount (5% = 0.05 etc)
/// </summary>

public decimal Value;
/// <summary>
/// True if Value is an amount
/// </summary>

public bool IsAmount;
/// <summary>
/// Optional reason code.
/// </summary>

public int? ReasonCode;
/// <summary>
/// Is transaction discount
/// </summary>

public bool IsTranDiscount;
}
```
**Response Body**: ItemResponse.

Example:
```json
{"RecoverableErrors":null,"Updates":{"NewItems":[],"ChangedItems":
[{"ItemCode":"0000126","ScanCode":"0000126","Description":"Tournament
yo-yo","Quantity":1.0,"UnitPrice":9.990000,"ExtendedPrice":9.99,
"DiscountAmount":-1.00,"TaxAmount":0.64,"UnitOfMessure":1,"VoidCode":0,
"IsItemAuthorizationRequired":false,"AccountToken":null,"ProratedDiscounts":
[{"Description":"Manual
Item
Percent","Amount":-1.00,"LineNumber":10}],"Proratedtaxes":
[{"Description":"NC-State
Tax","Amount":0.43,"IsVAT":false,"AuthorityId":37000,"Id":1,"LineNumber":1},{"Description":"Durham
Co.
Tax","Amount":0.21,"IsVAT":false,"AuthorityId":37063,"Id":1,"LineNumber":5}],
"LineNumber":7}],"SuggestedItems":null,"Taxes":[{"Description":"NC-State
Tax","Amount":0.43,"IsVAT":false,"AuthorityId":37000,"Id":1,"LineNumber":1},
{"Description":"Durham
Co.
Tax","Amount":0.21,"IsVAT":false,"AuthorityId":37063,"Id":1,"LineNumber":5}],
"Discounts":[{"Description":"Benign
coupon for
points","Amount":-0.010000,"LineNumber":9},{"Description":"Manual
Item
Percent","Amount":-1.00,"LineNumber":10}],
"SubTotal":9.99,"TaxTotal":0.64,"DiscountTotal":-1.00}}
```