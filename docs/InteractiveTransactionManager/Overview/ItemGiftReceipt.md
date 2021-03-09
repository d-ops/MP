---
layout: default
title: ItemGiftReceipt
nav_order: 26
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### ItemGiftReceipt 

This message is called to mark or unmark eligible line item as a gift
item and have the associated "gift receipt" support for that line item.
The request includes the line number of the item to be marked/unmarked
as well as Boolean true/false parameter to explicitly indicate how the
line should be marked.

If the Boolean parameter is true, then the line will be marked as a gift
item. If a line has been affected by the operation, then the response
will include details of the line and an indication of the gift status.
If the line was unaffected by the operation, then just the indication of
the line's current gift status will be included in the response.

The quantity field on the item line determines the number of gift
receipts printed for the line.

**Uri**: /baskets/{id}/items/{linenumber}/giftreceipts

**Http Verb**: POST

**Request Body**: Boolean gift receipt flag

**Response Body**:

See ItemUpdatesResponse above.
