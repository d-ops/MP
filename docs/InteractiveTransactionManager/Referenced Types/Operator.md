---
layout: default
title: Operator
parent: Referenced Types
grand_parent: Interactive Transaction Manager
has_children: true
---
### Operator 

A Store Employee currently signed on to a device and performing retail
workflows.
```csharp
public class Operator
{
/// <summary>
/// A unique identifier for the Operator with the store.
/// </summary>

public string Id { get; set; }
/// <summary
/// Worker Id
/// </summary>

public string WorkerId { get; set; }
/// <summary>
/// A culture name in the format languagecode2-country/regioncode2, such
as en-ENU for English.
/// </summary>

public string CultureName { get; set; }
}
```