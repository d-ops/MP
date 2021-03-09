---
layout: default
title: EndTransaction
nav_order: 53
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# EndTransaction
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is called to end the transaction.

## Uri
/baskets/{id}

##  Http Verb
POST

## Request Body
See TerminateRequest above (ReasonType = TerminationType.End)
