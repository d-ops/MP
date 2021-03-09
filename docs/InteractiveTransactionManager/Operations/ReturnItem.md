---
layout: default
title: ReturnItem
nav_order: 13
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# ReturnItem 
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is sent to actually return an item (no information return).
It will return details of the new item including taxes and any
discounts, updated transaction totals, plus potential changes to
previously sold items if the selling of the item triggers discounts on
previous items. The response will also include the line number of the
item in the transaction.

This is the same as BuyItem except ReasonCode ReturnItemRequest is used
instead of ItemRequest.
```csharp
public class ReturnItemRequest : ItemRequest
{
/// <summary>
/// For an item return this is the reason code.Should be null for a sale item.
/// </summary>

public int? ReasonCode;
/// <summary>
/// For a receipted return original selling location
/// </summary>

public int? SellingLocationId;
/// <summary>
/// For a receipted return original register number on which the item was sold
/// </summary>

public int? RegisterId;
/// <summary>
/// For a receipted return original transaction number in which the item was sold
/// </summary>

public int? TransactionId;
/// <summary>
/// For a receipted return start time of original basket in which the item was sold
/// </summary>

public DateTime? TransactionStartTime;
/// <summary>
/// Indicates if any applicable restocking fee should be added. Should be null unless a previous
/// error indicated an optional restocking fee was required
/// </summary>

public bool? AddRestockingFee;
}
```