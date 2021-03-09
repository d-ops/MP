---
layout: default
title: GetReceipt
nav_order: 48
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# GetReceipt
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is called to get a transaction receipt in ARTS Receipt XML
format. The request must include the original register, transaction id
and date. A receipt will only be available for transactions that have
been logged to the receipt repository.

## Uri
/receipts

## Http Verb
POST

## Request Body
```csharp
/// <summary>
/// Details for selecting a completed receipt
/// </summary>

public class ReceiptDataRequest
{
/// <summary>
/// Register number on which basket was completed
/// </summary>

public int RegisterNumber;
/// <summary>
/// Transaction number of basket
/// </summary>

public int TransactionNumber;
/// <summary>
/// Date on which transaction was started
/// </summary>

public DateTime TransactionStartDate;
/// <summary>
/// Email where receipt will be sent
/// </summary>
/// <returns></returns>

public string Email { get; set; }
}
```
## Response Body
string containing XML data
