---
layout: default
title: RestrictionDetails
parent: Referenced Types
grand_parent: Interactive Transaction Manager
has_children: true
---
### RestrictionDetails
```csharp
/// <summary>
/// Details about a restriction
/// </summary>

public class RestrictionDetails
{
/// <summary>
/// Displayable description of the restriction
/// </summary>

public string Description;
/// <summary>
/// Restriction type
/// </summary>

public RestrictionType RestrictionType;
/// <summary>
/// Restriction id
/// </summary>

public int RestrictionRuleId;
/// <summary>
/// Optional value for restriction: currently can only be required
customer age / operator age
/// </summary>

public int Value;
}
```