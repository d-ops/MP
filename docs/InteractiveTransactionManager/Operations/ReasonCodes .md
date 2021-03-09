---
layout: default
title: ReasonCodes
nav_order: 50
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# ReasonCodes  
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is used to get list of reason codes for a given reason code
group. The group ID is passed in the request, and if reason codes are
configured for the function, the corresponding reason codes list is
returned in the response. If the function does not have reason code
prompting configured, no list is returned. The description in the list
is based on the language of the operator / customer depending on device
type.

## Uri
/reasoncodes/{group}

## Http Verb
GET

## Response Body
An array of
```csharp
public class ReasonCodeDetails
{
/// <summary>
/// Value of reason code
/// </summary>

public int Value;
/// <summary>
/// Description of reason code in the operators language
/// </summary>

public string Description;
}
```