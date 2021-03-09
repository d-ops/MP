---
layout: default
title: AddOrderReturnItem
nav_order: 32
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### AddOrderReturnItem

This is used to return an item from a previously picked up order.

**Uri**: /baskets/{id}/orders/{orderid}/Items/{linenumber}

**Http Verb**: PUT

**Request Body**: OrderItemDetails from above

**Response Body**: OrderDetails from above (note Items array will
include only the item just returned)
