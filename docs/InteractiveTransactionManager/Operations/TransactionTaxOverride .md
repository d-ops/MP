---
layout: default
title: TransactionTaxOverride
nav_order: 37
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# TransactionTaxOverride  
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This message is called to perform a transaction tax or VAT override for
a given amount. The request must include the Amount and tax/Vat code
identifier; optionally a reason code may also be included in the
request. The response will include update totals and tax & line
information.

## URI
/baskets/{id}/taxauthorities/{authorityid}/taxes/{taxcode}

## Http Verb
POST

## Request body
See ManualTax above

## Response Body
See ItemUpdatesResponse
