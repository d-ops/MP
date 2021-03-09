---
layout: default
title: ChangeQuantity
nav_order: 25
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### ChangeQuantity 

This message is called to do a quantity change for a specified line
item. The request includes the line number and the new quantity for the
line item. The response will include updated totals and items list.

**Uri**: /baskets/{id}/items/{linenumber}/quantities

**Http Verb**: POST

**Request Body**: decimal quantity

**Response Body**:

See ItemUpdatesResponse above.
