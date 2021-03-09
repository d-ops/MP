---
layout: default
title: BasketIdentifier
parent: Referenced Types
grand_parent: Interactive Transaction Manager
has_children: true
---
### BasketIdentifier

Identifier for a basket
```csharp
/// <summary>
/// Identifier for a basket
/// </summary>

public class BasketIdentifier : ManagerResponseData
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