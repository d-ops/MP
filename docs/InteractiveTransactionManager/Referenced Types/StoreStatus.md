---
layout: default
title: StoreStatus
parent: Referenced Types
grand_parent: Interactive Transaction Manager
has_children: true
---
### StoreStatus 

The statuses a Store goes through during the course of a business day.
Indicates whether the Store has been opened for business.
```csharp
public enum StoreStatus
{
/// <summary>
/// Opening
/// </summary>

Opening = 1,

/// <summary>
/// Opened
/// </summary>

Opened = 2,

/// <summary>
/// Closing
/// </summary>

Closing = 3,

/// <summary>
/// Closed
/// </summary>

Closed = 4
}
```