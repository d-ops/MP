---
layout: default
title: TransactionDiscount
nav_order: 36
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### TransactionDiscount 

This message is called to perform a percentage or amount off transaction
discount. The request must include a Discount ID, it must be on file in
the Market Place database. Optionally a reason code may be included in
the request. The response will include the updated items and taxes list
and transaction totals.

**Uri**: /baskets/{id}/discounts

**Http Verb**: POST

**Request Body**: See ManualDiscount above

**Response Body**:

See ItemUpdatesResponse above.
