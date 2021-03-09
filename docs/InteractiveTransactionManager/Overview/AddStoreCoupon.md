---
layout: default
title: AddStoreCoupon
nav_order: 21
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
## AddStoreCoupon

This method adds the store coupon to the transaction. The response will
include updated transaction totals if any discount immediately triggered
and the line number of the item in the transaction. If any discounts
immediately trigger as a result of adding the coupon discount to the
transaction then these updates will be sent in the response. It will not
be possible to return details of future discounts associated with the
coupon that may trigger as additional items are added to the
transaction.

**Uri**: /baskets/{id}/storecoupons

**Http Verb**: POST

**Request Body**:
```csharp
public class StoreCouponRequest
{
/// <summary>
/// Item scan code
/// </summary>

public string ItemCode;
/// <summary>
/// True if item was scanned
/// </summary>

public bool IsScanned;
}
```
**Response Body**:

See ItemUpdatesResponse above.

Example:
```json
{"ChangedItems":[{"ItemCode":"0010071","ScanCode":"0010071","Description":"Faux
Suede
Jacket","Quantity":1.0,"UnitPrice":44.990000,"ExtendedPrice":44.99,"DiscountAmount":-10.00,"TaxAmount":2.48,"UnitOfMessure":1,"VoidCode":0,"IsItemAuthorizationRequired":false,"AccountToken":null,"ProratedDiscounts":[{"Description":"Jacket
Coupon","Amount":-10.00,"LineNumber":14}],"Proratedtaxes":[{"Description":"NC-State
Tax","Amount":1.68,"IsVAT":false,"AuthorityId":37000,"Id":1,"LineNumber":1},{"Description":"Durham
Co.
Tax","Amount":0.80,"IsVAT":false,"AuthorityId":37063,"Id":1,"LineNumber":5}],"LineNumber":13}],"Taxes":[{"Description":"NC-State
Tax","Amount":1.68,"IsVAT":false,"AuthorityId":37000,"Id":1,"LineNumber":1},{"Description":"Durham
Co.
Tax","Amount":0.97,"IsVAT":false,"AuthorityId":37063,"Id":1,"LineNumber":5},{"Description":"NC-State
Tax","Amount":0.07,"IsVAT":false,"AuthorityId":37000,"Id":-1,"LineNumber":11}],"Discounts":[{"Description":"Benign
coupon for
points","Amount":-0.010000,"LineNumber":9},{"Description":"Manual
Item
Percent","Amount":-0.80,"LineNumber":10},{"Description":"Jacket
Coupon","Amount":-10.00,"LineNumber":14}],"SubTotal":52.99,"TaxTotal":2.72,"DiscountTotal":-10.80}
```