---
layout: default
title: VoidTransaction
nav_order: 47
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# VoidTransaction 
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is called to void the transaction if the customer decides
not to complete the transaction or if the transaction is deemed by the
client system to have been abandoned.

Optionally a reason code may be included in the request. If the
transaction contains authorized item or tenders, these items must be
explicitly voided prior to voiding the transaction.

## Uri
/baskets/{id}

## Http Verb
POST

## Request Body
See TerminateRequest above
(ReasonType=TerminationType.Void)
