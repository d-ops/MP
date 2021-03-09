---
layout: default
title: LookupStoreCoupon
nav_order: 20
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
#LookupStoreCoupon
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This method looks up the store coupon. It will return the coupon
description.

## Uri
/storecoupons/{itemcode}

## Http Verb
GET

## Response body
```csharp
public class StoreCouponInformation
{
/// <summary>
/// Store coupon description from DiscountDescription table
/// </summary>

public string Description;
/// <summary>
/// Discount amount
/// </summary>

public decimal Amount;
}
```
## Example
```json
{"Description":"Jacket Coupon","Amount":10.000000}
```