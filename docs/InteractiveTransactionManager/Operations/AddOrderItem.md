---
layout: default
title: AddOrderItem
nav_order: 31
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
# AddOrderItem
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This is used to add an item to an order ( orderid is the Group above )

## Uri
/baskets/{id}/orders/{orderid}/Items

## Http Verb
POST

## Request Body
InventoryItemDetails from above

## Response Body
OrderDetails from above (note Items array will include only the item just added)

## Example
```json
{"Number":null,"Group":1,"Status":0,"CustomerId":"6100000011","Total":10.740000,"BalanceDue":0.000000,"DeliveryFees":0.0,"CancellationFees":0.0,"Destination":1,"DeliveryAddress":"dsdd","DeliveryId":"1022","Items":[{"ExternalItemCode":"Tournament
yo-yo","ItemCode":"0000126","Description":"Tournament
yo-yo","Quantity":1.0,"UnitPrice":0.0,"ExtendedPrice":9.99,"DiscountAmount":-0.25,"TaxAmount":1.0,"UnitOfMessure":0,"Status":0,"OrderLineNumber":0,"BasketLineNumber":9,"ReasonCode":0,"ReasonCodeDescription":null,"FeeTotal":0.0}]}
```