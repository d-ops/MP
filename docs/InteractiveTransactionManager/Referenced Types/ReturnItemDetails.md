---
layout: default
title: ReturnItemDetails
parent: Referenced Types
grand_parent: Interactive Transaction Manager
has_children: true
---
### ReturnItemDetails 

Return item within basket
```csharp
public class ReturnItemDetails : ItemDetails
{
/// <summary>
/// Selected return reason
/// </summary>

[DataMember]

public string ReturnReason;
}
```