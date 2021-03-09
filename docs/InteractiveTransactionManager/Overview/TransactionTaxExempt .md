---
layout: default
title: TransactionTaxExempt
nav_order: 38
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### TransactionTaxExempt 

This message is called to perform a transaction tax or VAT exemption.
The request must contain an exemption identifier and a tax or VAT code
identifier. Any previous exemptions at a line level or transaction level
for the given tax code are replaced by new transaction level exemptions.
The response will include updated totals and items list (including
taxes).

**URI**: /baskets/{id}/taxauthorities/{authorityid}/exemptions/{taxcode}

**Http Verb**: POST

**Request body**: See ManualTaxExemption above

**Response Body**: See ItemUpdatesResponse
