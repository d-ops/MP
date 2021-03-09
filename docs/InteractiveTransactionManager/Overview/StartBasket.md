---
layout: default
title: StartBasket
nav_order: 5
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### StartBasket 

This message is sent to start a new basket. It has an optional parameter
to start a basket other than a sales basket. The basket will be
persisted in the memory cache between calls.

**Uri**: /baskets

**Http Verb**: POST

**Request body**:

Int? transactionCode

**Response body data**:
```csharp
/// <summary>
/// Identifier for a basket
/// </summary>

public class BasketIdentifier
{
/// <summary>
/// Unique identifier for the basket
/// </summary>

public Guid Id;

/// <summary>
/// Transaction number for the basket
/// </summary>

public int TransactionNumber;
}
```
Example:
```json
{"Id":"a206f48b-9fba-4aaa-b723-2b95d577211a","TransactionNumber":2}
```