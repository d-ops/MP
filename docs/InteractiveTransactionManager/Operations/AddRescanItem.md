---
layout: default
title: AddRescanItem
nav_order: 18
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# AddRescanItem 
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is used to add details of an item that failed to be added
to transaction but is a recoverable by a rescan i.e. not on file,
quantity required, weight required, price required, age restricted or
unexpected errors. Details of these items will be saved internally in
the basket but will not be added to the basket in the normal way i.e.
they will not affect transaction totals or transaction discounts in any
way.

If Rescan items exist in the transaction, tender is not available via
ITM i.e. the transaction must be completed on a full register.

## Uri
/baskets/{id}/rescanitems

## Http Verb
POST

## Request body
```c#
public class RescanItemRequest
{
/// <summary>
/// Item scan code
/// </summary>

public string ItemCode;
/// <summary>
/// Optional item quantity
/// </summary>

public decimal? Quantity;
/// <summary>
/// True if item was scanned
/// </summary>

public bool IsScanned;
}
```
## Response body

Unique Integer value indicating the line number of the rescan item in
the basket
