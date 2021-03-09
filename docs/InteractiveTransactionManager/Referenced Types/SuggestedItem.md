---
layout: default
title: SuggestedItem
parent: Referenced Types
grand_parent: Interactive Transaction Manager
has_children: true
---
### SuggestedItem 

Details about a suggested item.
```csharp
public class SuggestedItem
{
/// <summary>
/// Item code
/// </summary>

[DataMember]

public string ItemCode;
/// <summary>
/// Description
/// </summary>

[DataMember]

public string Description;
/// <summary>
/// Retail price
/// </summary>

[DataMember]

public decimal RetailPrice;
}
```