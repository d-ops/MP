---
layout: default
title: LookupSuspendedBaskets
nav_order: 8
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### LookupSuspendedBaskets

This is used to get the details about all suspended baskets that have
not currently been resumed.

**Uri**: /suspends

Http Verb: GET

**Response body data**:

An array of:
```csharp
public class SuspendDetails
{
/// <summary>
/// Unique identifier for suspended basket
/// </summary>

Guid Id

/// <summary>
/// Selling location number where basket was suspended
/// </summary>

int SellingLocationId;
/// <summary>
/// Register number on which the basket was suspended
/// </summary>

public int TerminalNumber;
/// <summary>
/// Transaction number of suspended basket
/// </summary>

int TransactionId;
/// <summary>
/// Transaction start time of suspended basket
/// </summary>

DateTimeOffset TransactionDateTime;
/// <summary>
/// Worker id of operator who performed the suspend
/// </summary>

string WorkerId;
/// <summary>
/// Transaction total of suspended basket
/// </summary>

decimal TransactionTotal;
/// <summary>
/// Reason for suspend
/// </summary>

public string SuspendReason;
}
```
Example:
```json
[{"Id":"25c1af53-cfbe-4d2a-8515-e40a7394705f","SellingLocationId":1021,"TerminalNumber":1,"TransactionId":3,"TransactionDateTime":"2015-02-20T16:28:00.4718466-05:00","WorkerId":"111","TransactionTotal":56.740000,"SuspendReason":"Go
Get Wallet"}]
```