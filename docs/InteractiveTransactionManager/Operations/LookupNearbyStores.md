---
layout: default
title: LookupNearbyStores
nav_order: 27
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
#LookupNearbyStores
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This is used to return the addresses of nearby stores.

## Uri
/nearbystores

## Http Verb
GET

## Response Body
Array of
```csharp
public class StoreInformation
{
/// <summary>
/// Store id.
/// </summary>

public string StoreId;
/// <summary>
/// Name of store.
/// </summary>

public string StoreName;
/// <summary>
/// Address.
/// </summary>

public string StoreAddress;
}
```
## Example
```json
[{"StoreId":"111","StoreName":"Mega
Store","StoreAddress":"New York, Wall street
3"},{"StoreId":"222","StoreName":"Media
Markt","StoreAddress":"Kazan, Peterburgskaya street
9"},{"StoreId":"333","StoreName":"Underground
Store","StoreAddress":"Bangladesh, Unnamed street 10"}]
```