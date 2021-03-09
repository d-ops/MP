---
layout: default
title: LineItemTaxExempt
nav_order: 16
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### LineItemTaxExempt 

This message is called to perform a line item tax exemption. A tax (or
VAT) code, a line number being exempted and the Exempt ID must be
included in the request. Optionally a reason code may be included in the
request. The response will include the updated items and taxes lists and
totals.

**URI**:
/baskets/{id}/items/{linenumber}/taxauthorities/{authorityid}/exemptions/{taxcode}

**Http Verb**: POST

**Request body**:
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
**Response Body**: TaxOverrideResponse.
