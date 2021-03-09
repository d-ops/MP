---
layout: default
title: CreateOrder
nav_order: 30
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### CreateOrder

This is used to create an order. This will include customer details and
delivery information. The delivery information must be obtained by the
client application. Customer must have been added to the basket by the
AddCustomer method before this is called.

**Uri**: /basket/{id}/orders

**Http Verb**: POST

**Request Body**:
```csharp
public class CreateOrderRequest
{
/// <summary>
/// Where the order is to be delivered (store or customer)
/// </summary>

public DeliveryDestination Destination;
/// <summary>
/// Delivery address
/// </summary>

public string DeliveryAddress;
/// <summary>
/// If a store delivery then store id or a customer id for a customer delivery
/// </summary>

public string DeliveryId;
}
```

**Response Body**: OrderDetails from above.

Example:
```json
{"Number":null,"Group":1,"Status":0,"CustomerId":"6100000011","Total":0.0,"BalanceDue":0.0,"DeliveryFees":0.0,"CancellationFees":0.0,"Destination":1,"DeliveryAddress":"dsdd","DeliveryId":"1022","Items":[]}
```