---
layout: default
title: TransactionTaxOverride
nav_order: 37
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### TransactionTaxOverride  

This message is called to perform a transaction tax or VAT override for
a given amount. The request must include the Amount and tax/Vat code
identifier; optionally a reason code may also be included in the
request. The response will include update totals and tax & line
information.

**URI**: /baskets/{id}/taxauthorities/{authorityid}/taxes/{taxcode}

**Http Verb**: POST

**Request body**: See ManualTax above

**Response Body**: See ItemUpdatesResponse
