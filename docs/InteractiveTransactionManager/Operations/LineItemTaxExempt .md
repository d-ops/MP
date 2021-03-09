---
layout: default
title: LineItemTaxExempt
nav_order: 16
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# LineItemTaxExempt 
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is called to perform a line item tax exemption. A tax (or
VAT) code, a line number being exempted and the Exempt ID must be
included in the request. Optionally a reason code may be included in the
request. The response will include the updated items and taxes lists and
totals.

## URI
/baskets/{id}/items/{linenumber}/taxauthorities/{authorityid}/exemptions/{taxcode}

## Http VerbPOST

## Request body
```csharp
public class ManualTaxExemption
{
/// <summary>
/// Exemption id
/// </summary>

public string ExemptionId;
/// <summary>
/// Optional reason code
/// </summary>

public int? ReasonCode;
/// <summary>
/// Is transaction mode
/// </summary>

public bool IsTranTaxMod;
}
```
## Response Body
TaxOverrideResponse
