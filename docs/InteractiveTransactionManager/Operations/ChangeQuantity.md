---
layout: default
title: ChangeQuantity
nav_order: 25
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# ChangeQuantity 
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is called to do a quantity change for a specified line
item. The request includes the line number and the new quantity for the
line item. The response will include updated totals and items list.

## Uri
/baskets/{id}/items/{linenumber}/quantities

## Http Verb
POST

## Request Body
decimal quantity

## Response Body

See ItemUpdatesResponse above.
