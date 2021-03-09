---
layout: default
title: VoidTransaction
nav_order: 47
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### VoidTransaction 

This message is called to void the transaction if the customer decides
not to complete the transaction or if the transaction is deemed by the
client system to have been abandoned.

Optionally a reason code may be included in the request. If the
transaction contains authorized item or tenders, these items must be
explicitly voided prior to voiding the transaction.

**Uri**: /baskets/{id}

**Http Verb**: POST

**Request Body**: See TerminateRequest above
(ReasonType=TerminationType.Void)
