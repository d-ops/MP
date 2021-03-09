---
layout: default
title: AddTransactionNofStoreCoupon
nav_order: 23
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### AddTransactionNofStoreCoupon 

This method adds a not on file transaction store coupon to the
transaction. The response will include updated transaction totals if any
discount immediately triggered and the line number of the item in the
transaction. If any discounts immediately trigger as a result of adding
the coupon discount to the transaction then these updates will be sent
in the response. It will not be possible to return details of future
discounts associated with the coupon that may trigger as additional
items are added to the transaction.

**Uri**: /baskets/{id}/items/{linenumber}/nofstorecoupons

**Http Verb**: POST

**Request Body**:
```csharp
public class NofStoreCouponRequest
{
/// <summary>
/// Item scan code
/// </summary>

public string ItemCode;
/// <summary>
/// True if item was scanned
/// </summary>

public bool IsScanned;
/// <summary>
/// True if Value is an amount
/// </summary>

public bool IsAmount;
/// <summary>
/// Store coupon discount value - amount or percentage amount
/// </summary>

public decimal Value;
/// <summary>
/// Is transaction discount
/// </summary>

public bool IsTransDiscount;
/// <summary>
/// The reason code
/// </summary>

public int? ReasonCode;
}
```
**Response Body**:

See ItemUpdatesResponse above.
