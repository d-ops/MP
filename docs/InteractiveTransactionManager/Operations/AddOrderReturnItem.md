---
layout: default
title: AddOrderReturnItem
nav_order: 32
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# AddOrderReturnItem
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This is used to return an item from a previously picked up order.

## Uri
/baskets/{id}/orders/{orderid}/Items/{linenumber}

## Http Verb
PUT

## Request Body
OrderItemDetails from above

## Response Body
OrderDetails from above (note Items array will include only the item just returned)
