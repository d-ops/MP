---
layout: default
title: LineItemTaxOverride
nav_order: 15
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# LineItemTaxOverride 
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is called to perform a line item tax override by an Amount.
The line number, a tax code and amount are included in the request.
Optionally a reason code may be also included. The response will include
the new tax information related to the line #.

## URI
/baskets/{id}/items/{linenumber}/taxauthorities/{authorityid}/taxes/{taxcode}

## Http Verb
POST

## Request body
```csharp
public class ManualTax
{
/// <summary>
/// New tax rate percentage for the tax code
/// </summary>

public decimal TaxRate;
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
```csharp
public class TaxOverrideResponse
{
/// <summary>
/// Updated item
/// </summary>

public ItemDetails UpdatedItem;
/// <summary>
/// Tax details
/// </summary>

public TaxDetails UpdatedTax;
/// <summary>
/// Total tax amount
/// </summary>

public decimal TaxTotal;
}
```
## Example
```json
{"UpdatedItem":{"ItemCode":"0000126","ScanCode":"0000126","Description":"Tournament
yo-yo","Quantity":1.0,"UnitPrice":9.990000,"ExtendedPrice":9.99,"DiscountAmount":-1.00,"TaxAmount":0.30,"UnitOfMessure":1,"VoidCode":0,"IsItemAuthorizationRequired":false,"AccountToken":null,"ProratedDiscounts":[{"Description":"Manual
Item
Percent","Amount":-1.00,"LineNumber":10}],"Proratedtaxes":[{"Description":"NC-State
Tax","Amount":0.09,"IsVAT":false,"AuthorityId":37000,"Id":-1,"LineNumber":11},{"Description":"Durham
Co.
Tax","Amount":0.21,"IsVAT":false,"AuthorityId":37063,"Id":1,"LineNumber":5}],"LineNumber":7},"UpdatedTax":{"Description":"NC-State
Tax","Amount":0.0,"IsVAT":false,"AuthorityId":37000,"Id":1,"LineNumber":1},"TaxTotal":0.30}
```