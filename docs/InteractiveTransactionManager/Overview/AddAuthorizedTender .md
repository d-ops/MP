---
layout: default
title: AddAuthorizedTender
nav_order: 41
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### AddAuthorizedTender

This message is called to add an already authorized tender to the
transaction -- the ValidateAuthorizedTender method above should be
called prior to authorization. The tender type, amount and authorization
provider response information is included in the request. The response
will include updated totals information and the list of tenders
currently in the transaction.

**Uri**: /baskets/{id}/tenders

**Http Verb**: POST

**Request Body**:
```csharp
public class TenderRequest
{
/// <summary>
/// Requested amount
/// </summary>

public decimal RequestedAmount;
/// <summary>
/// Authorized amount
/// </summary>

public decimal AuthorizedAmount;
/// <summary>
/// Tender code
/// </summary>

public int TenderCode;
/// <summary>
/// The type of the account (gift card, check, Visa, MC, debit, EBT,etc.)
/// </summary>

public virtual AccountTypeCode? AccountType { get; set; }
/// <summary>
/// Account number token
/// </summary>

public string AccountNumberToken;
/// <summary>
/// System trace audit number returned from device
/// </summary>

public string STAN;
/// <summary>
/// For an authorized item authorization code from authorizer for the
sale
/// </summary>

public string AuthorizationCode;
/// <summary>
/// For an authorized item response token from authorizer for the sale
/// </summary>

public string ResponseToken;
/// <summary>
/// Authorization time
/// </summary>

public DateTimeOffset AuthorizationTime;
/// <summary>
/// The result
/// </summary>

public AuthorizationResultEnums Result;
/// <summary>
/// The result details
/// </summary>

public AuthorizationDetailEnums ResultDetails;
}
```
**Response Body**:

```csharp
public class TenderUpdatesResponse

{
/// <summary>
/// Tender details
/// </summary>

public TenderDetails[] Tenders;
/// <summary>
/// Total extended amount of items
/// </summary>

public decimal SubTotal;
/// <summary>
/// Total tax amount
/// </summary>

public decimal TaxTotal;
/// <summary>
/// Total discount amount
/// </summary>

public decimal DiscountTotal;
/// <summary>
/// Total tendered amount
/// </summary>

public decimal TenderTotal;
}
```
Example:
```json
{"Tenders":[{"Description":"VISA","Amount":-10.70,"TenderCode":5,"AccountToken":"XXXXXXXXXXXXXXXXX","SignatureData":null,"LineNumber":10}],"SubTotal":9.99,"TaxTotal":0.71,"DiscountTotal":0.0,"TenderTotal":-10.70}
```