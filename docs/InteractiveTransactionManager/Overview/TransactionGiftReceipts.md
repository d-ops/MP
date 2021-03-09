---
layout: default
title: TransactionGiftReceipts
nav_order: 39
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### TransactionGiftReceipts 

This message is called to mark or unmark all eligible line items in a
transaction as gift items and have the associated "gift receipt" support
for those line items. There is a Boolean true/false parameter to
explicitly indicate how the line should be marked.

If the Boolean parameter is true, then all eligible lines will be marked
as a gift items. All lines that have been affected by the operation will
have their details returned in the response as well as an overall
indication of the gift status. Lines in the transaction unaffected by
the operation will not be returned in the response.

**Uri**: /baskets/{id}/giftreceipts

**Http Verb**: POST

**Request Body**: Boolean gift receipt flag

**Response Body**:

See ItemUpdatesResponse above.
