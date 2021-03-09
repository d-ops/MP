---
layout: default
title: BuyItem
nav_order: 12
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# BuyItem
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is sent to actually sell an item. It will return details of
the new item including taxes and any discounts, updated transaction
totals, plus potential changes to previously sold items if the selling
of the item triggers discounts on previous items. The response will also
include the line number of the item in the transaction.

The message will include the item code and optional quantity / weight,
price, serial number, employee id for commission, and satisfied
restriction identifiers with values. In general the optional values will
only be set if the buy of an item fails because it was quantity required
/ weight required / serial number required / commissioned item or had
restrictions like customer age.

If the sales associate cannot complete the selling of the item then
AddRescanItem can be used to mark the item for rescan at a full POS.

## Uri
/baskets/{id}/items

## Http Verb
POST

## Request Body

An array of:
```csharp
public class ItemRequest
{
/// <summary>
/// Item scan code
/// </summary>

public string ItemCode;
/// <summary>
/// True if item was scanned
/// </summary>

public bool IsScanned;
/// <summary>
/// On retry of an item sale the line number of item that failed
/// </summary>

public int? LineNumber;
/// <summary>
/// Optional quantity / weight
/// </summary>

public decimal? Quantity;
/// <summary>
/// Manually entered item price
/// </summary>

public decimal? UnitPrice;
/// <summary>
/// Optional serial number for a serialized item
/// </summary>

public string SerialNumber;
/// <summary>
/// Optional employee id receiving commission for a commissioned item
/// </summary>

public string EmployeeId;
/// <summary>
/// Customer birth date
/// </summary>

DateTime? CustomerBirthDate;
/// <summary>
/// For an authorized item the masked account number
/// </summary>

public string MaskedAccountNumber;
/// <summary>
/// For an authorized item STAN returned from device
/// </summary>

public string STAN;
/// <summary>
/// For an authorized item authorization code from authorizer for the sale
/// </summary>

public string AuthorizationCode;
/// <summary>
/// For an authorized item response token from authorizer for the sale
/// </summary>

public string ResponseToken;
/// <summary>
/// For an authorized item authorization time
/// </summary>

public DateTimeOffset? AuthorizationTime;
/// <summary>
/// List of restrictions rule ids satisified by operator (can only be item check and signature required currently)
/// Note if multiple restrictions need to be satisfied for selling an item then all must be included
/// </summary>

int[] SatisfiedRestrictions;
}
```
## Response Body
```csharp
/// <summary>
/// Response to selling of an item
/// </summary>

public class ItemResponse
{
/// <summary>
/// Errors that can be recovered by the operator i.e. price required /quantity required etc.
/// </summary>

public ErrorItem[] RecoverableErrors;
/// <summary>
/// If selling of the item completed then this describes the changes
that resulted in the basket
/// </summary>

public ItemUpdates Updates;
}
```
Or if the item code was a customer id then a CustomerResponse will be
returned.

Note: there will only be more than one if the item had linked or set
items associated and the selling of the item failed with a retryable
error. There must be one ItemRequest for each ErrorItem in the response
in the same order as in the response.

The client application must set the requested information in each item
in the list. So let's say that item X was sold and it included set items
Y and Z. Item Y was a serial number required item. Item Z had a customer
age restriction. In this case there will be 3 error items in the
response -- X, Y, Z.

Operator then collects the serial number. It should be entered into item
Y reformatted as an ItemRequest.

Finally operator verifies the customer age and enters it into item Z
reformatted as an ItemRequest.

Application should then retry the selling of the item including a
reformatted X, Y, Z in the request.

Item restrictions are handled in a similar way (item check and signature
required are the only two currently supported).

## Example
```json
{"RecoverableErrors":null,"Updates":{"NewItems":
[{"ItemCode":"051009120015","ScanCode":"051009120015",
"Description":"Striped Logo Top","Quantity":1.0,
"UnitPrice":24.000000,"ExtendedPrice":24.00,
"DiscountAmount":-12.00,"TaxAmount":0.86,
"UnitOfMessure":1,"VoidCode":0,
"IsItemAuthorizationRequired":false,
"AccountToken":null,"ProratedDiscounts":
[{"Description":"Buy One Get One","Amount":-12.00,"LineNumber":11}],
"Proratedtaxes":
[{"Description":"NC-State Tax","Amount":0.58,"IsVAT":false,
"AuthorityId":37000,"Id":1,"LineNumber":1},
{"Description":"Durham Co. Tax","Amount":0.28,
"IsVAT":false,"AuthorityId":37063,"Id":1,"LineNumber":5}],
"LineNumber":12}],"ChangedItems":
[{"ItemCode":"051009120015","ScanCode":"051009120015",
"Description":"Striped Logo Top","Quantity":1.0,
"UnitPrice":24.000000,"ExtendedPrice":24.00,
"DiscountAmount":-12.00,"TaxAmount":0.84,
"UnitOfMessure":1,"VoidCode":0,
"IsItemAuthorizationRequired":false,"AccountToken":null,
"ProratedDiscounts":
[{"Description":"Buy One Get One","Amount":-12.00,"LineNumber":11}],
"Proratedtaxes":
[{"Description":"NC-State Tax","Amount":0.57,"IsVAT":false,
"AuthorityId":37000,"Id":1,"LineNumber":1},
{"Description":"Durham Co. Tax","Amount":0.27,"IsVAT":false,
"AuthorityId":37063,"Id":1,"LineNumber":5}],"LineNumber":10}],
"SuggestedItems":null,"Taxes":
[{"Description":"NC-State Tax","Amount":1.63,"IsVAT":false,
"AuthorityId":37000,"Id":1,"LineNumber":1},
{"Description":"Durham Co. Tax","Amount":0.78,"IsVAT":false,
"AuthorityId":37063,"Id":1,"LineNumber":5}],
"Discounts":[{"Description":"Benign coupon for points",
"Amount":-0.010000,"LineNumber":9},
{"Description":"Buy One Get One","Amount":-24.00,"LineNumber":11}],
"SubTotal":57.99,"TaxTotal":2.41,"DiscountTotal":-24.00}}
Benign coupon for points",
"Amount":-0.010000,"LineNumber":9},
{"Description":"Buy One Get One","Amount":-24.00,"LineNumber":11}],
"SubTotal":57.99,"TaxTotal":2.41,"DiscountTotal":-24.00}}
```