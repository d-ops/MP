---
layout: default
title: ValidateAuthorizedTender
nav_order: 40
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### ValidateAuthorizedTender 

This message is called to validate the tender prior to authorization by
the client. The tender type and amount is included in the request. It is
the responsibility of the client application to ensure the transaction
is not over tendered.

Tendering is not allowed if non voided "Re-Scan" item(s) exist in the
transaction. A transaction tender balance must be fulfilled before the
transaction can be ended using the End Transaction message.

Authorization is entirely the responsibility of a 3^rd^ party system.
Any data passed on this interface must be sufficiently masked and/or
tokenized.

If this validation call succeeds then the tender can be authorized by
the client and commited by calling the AddAuthorizedTender method below.
The details must be the same so that no possible validation errors are
detected.

**Uri**: /baskets/{id}/tenders

**Http Verb**: PUT

**Request Body**:
```csharp
public class TenderValidateRequest
{
/// <summary>
/// Requested amount
/// </summary>

public decimal Amount;
/// <summary>
/// Tender code
/// </summary>

public int TenderCode;
/// <summary>
/// Account number token
/// </summary>

public string AccountNumberToken;
}
```
HttpStatus.OK returned if validation is successful. Otherwise an error
message will be returned.
