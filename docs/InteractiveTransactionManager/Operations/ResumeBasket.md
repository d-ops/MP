---
layout: default
title: ResumeBasket
nav_order: 7
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# ResumeBasket 
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This is called to resume a previously suspended transaction using the id
of the original. Can only be called when a basket is not currently
active.

## Uri
/suspends/{id}

## Http Verb
DELETE

## Response body data

BasketDetails : see above.
