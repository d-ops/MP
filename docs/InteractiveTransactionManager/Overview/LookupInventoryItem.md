---
layout: default
title: LookupInventoryItem
nav_order: 29
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### LookupInventoryItem 

This is used to lookup an item from inventory.

**Uri**: /inventoryitems

**Http Verb**: GET

**Request Body**:
```csharp
public class InventoryItemRequest
{
/// <summary>
/// Search by item code
/// </summary>

public string ItemCode;
/// <summary>
/// Search by item description
/// </summary>

public string ItemDescription;
/// <summary>
/// Date on which the item is required
/// </summary>

public DateTime? DateRequired;
/// <summary>
/// True if its an enterprise search. Otherwise its for nearby stores.
/// </summary>

public bool IsEnterpriseSearch;
}
```
**Response Body**: Array of
```csharp
public class InventoryItemDetails
{
/// <summary>
/// Item ID to pass for external systems, e.g. SAP
/// </summary>

public string ExternalItemCode { get; set; }
/// <summary>
/// Location
/// </summary>

public string Location;
/// <summary>
/// Current quantity available
/// </summary>

public virtual Decimal CurrentQuantity { get; set; }
/// <summary>
/// Quantity in Transit
/// </summary>

public virtual Decimal QuantityInTransit { get; set; }
/// <summary>
/// Next delivery date
/// </summary>

public virtual DateTime NextDeliveryDate { get; set; }
/// <summary>
/// Item code
/// </summary>

public string ItemCode;
/// <summary>
/// Item description
/// </summary>

public string Description;
/// <summary>
/// Unit price
/// </summary>

public decimal UnitPrice;
}
```
Example:
```json
[{"Location":"Mega
Store","ItemCode":"0000126","Description":"Tournament
yo-yo","UnitPrice":0.0,"ExternalItemCode":"Tournament
yo-yo","CurrentQuantity":0.0,"QuantityInTransit":0.0,
"NextDeliveryDate":"2015-02-24T00:00:00-05:00"},
{"Location":"Media
Markt","ItemCode":"0000126","Description":"Tournament
yo-yo","UnitPrice":0.0,"ExternalItemCode":"Tournament
yo-yo","CurrentQuantity":0.0,"QuantityInTransit":2.0,
"NextDeliveryDate":"2015-03-02T00:00:00-05:00"}]
```