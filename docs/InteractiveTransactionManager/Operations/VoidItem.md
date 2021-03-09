---
layout: default
title: VoidItem
nav_order: 24
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# VoidItem 
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This method is called to void an item / store coupon. The line number of
the item to be voided will be specified in the request, and an optional
reason code. The response will include the updated transaction totals,
the same item details as when the item was added to the transaction plus
any updates to other items if discounts were activated / deactivated by
voiding the item.

If the line being voided is an authorized item, the provider response
data must also be included in the request.

## Uri
/baskets/{id}/items/{linenumber}

## Http Verb
POST (cannot be DELETE as a DELETE has no request body)

## Request Body
```csharp
public class VoidRequest
{
/// <summary>
/// Optional reason code
/// </summary>

public int? ReasonCode;
/// <summary>
/// STAN from authorizer for the void
/// </summary>

public string STAN;
/// <summary>
/// Token from authorizer for the void
/// </summary>

public string ResponseToken;
/// <summary>
/// Time at which the reveral occurred
/// </summary>

public DateTimeOffset? AuthorizationTime;
/// <summary>
/// Authorization result
/// </summary>

public AuthorizationResultEnums Result;
}
```
## Response Body

See ItemUpdatesResponse above.

## Example
```json
{"ChangedItems":[{"ItemCode":"0000126","ScanCode":"0000126",
"Description":"Tournament
yo-yo","Quantity":1.0,"UnitPrice":9.990000,"ExtendedPrice":0.0,
"DiscountAmount":0.0,"TaxAmount":0.0,"UnitOfMessure":1,"VoidCode":2,
"IsItemAuthorizationRequired":false,"AccountToken":null,
"ProratedDiscounts":null,"Proratedtaxes":null,"LineNumber":7}],
"Taxes":null,"Discounts":null,"SubTotal":0.0,"TaxTotal":0.0,
"DiscountTotal":0.0}
```