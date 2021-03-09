---
layout: default
title: LookupOrders
nav_order: 28
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### LookupOrders 

This is used to lookup orders associated with a customer identified by
customer id. Customer must have been looked up earlier with the
LookupCustomer method.

**Uri**: /orders/customers/{customerid}

**Http Verb**: GET

**Response Body**: Array of
Array of
```csharp
/// Details about an order
/// </summary>

public class OrderDetails
{
/// <summary>
/// Unique order number
/// </summary>

public string Number;
/// <summary>
/// Unique order group
/// </summary>

public int Group;
/// <summary>
/// Order status
/// </summary>

public OrderStatus Status;
/// <summary>
/// Customer id.
/// </summary>

public string CustomerId;
/// <summary>
/// Order total
/// </summary>

public decimal Total;
/// <summary>
/// Order balance due
/// </summary>

public decimal BalanceDue;
/// <summary>
/// Order delivery fees
/// </summary>

public decimal DeliveryFees;
/// <summary>
/// Order cancelattion fees
/// </summary>

public decimal CancellationFees;
/// <summary>
/// Where the order is to be delivered ( store or customer )
/// </summary>

public DeliveryDestination Destination;
/// <summary>
/// Delivery address
/// </summary>

public string DeliveryAddress;
/// <summary>
/// If a store delivery then store id or a customer id for a customer
delivery
/// </summary>

public string DeliveryId;
/// <summary>
/// Order items
/// </summary>

public OrderItemDetails[] Items;
}
```
Example:
```json
[{"Number":"1000","Group":1,"Status":1,"CustomerId":"6100000011",
"Total":44.870000,"BalanceDue":0.000000,"DeliveryFees":0.0,
"CancellationFees":0.0,"Destination":1,"DeliveryAddress":"100
Main Street, Durham, NC,
27707","DeliveryId":"1022","Items":[{"ExternalItemCode":"Faux
Suede Jacket","ItemCode":"0010071","Description":"Faux Suede
Jacket","Quantity":1.0,"UnitPrice":0.0,"ExtendedPrice":43.870000,
"DiscountAmount":0.0,"TaxAmount":0.0,"UnitOfMessure":0,"Status":0,
"OrderLineNumber":0,"BasketLineNumber":10,"ReasonCode":0,
"ReasonCodeDescription":null,"FeeTotal":0.0}]},
{"Number":"1001","Group":1,"Status":1,"CustomerId":"6100000011",
"Total":42.920000,"BalanceDue":0.000000,"DeliveryFees":0.0,
"CancellationFees":0.0,"Destination":1,"DeliveryAddress":"100
Main Street, Durham, NC,
27707","DeliveryId":"1022","Items":[{"ExternalItemCode":"Career
Jacket","ItemCode":"0010017","Description":"Career
Jacket","Quantity":1.0,"UnitPrice":0.0,"ExtendedPrice":41.920000,
"DiscountAmount":0.0,"TaxAmount":0.0,"UnitOfMessure":0,"Status":0,
"OrderLineNumber":0,"BasketLineNumber":12,"ReasonCode":0,
"ReasonCodeDescription":null,"FeeTotal":0.0}]}]
```