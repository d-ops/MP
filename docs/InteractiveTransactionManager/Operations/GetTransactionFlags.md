---
layout: default
title: GetTransactionFlags
nav_order: 44
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---

# GetTransactionFlags
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
The server will maintain a set of transaction flags that the client
system can interrogate using this method and update using
SetTransactionFlags message. This will be an integer value containing
bits whose meaning is defined by the clients to this system. These flags
will have no meaning to Market Place and will be transparently logged in
the POSLog record.

## Uri
/baskets/{id}/flags

## Http Verb
GET

## Response Body
integer flags
