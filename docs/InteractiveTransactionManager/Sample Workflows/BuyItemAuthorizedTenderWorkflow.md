---
layout: default
title: Buy Item / Authorized Tender Workflow
nav_order: 2
parent: Sample Workflow
grand_parent: Interactive Transaction Manager
has_children: true
---

### Buy Item / Authorized Tender Workflow

Initial Workflow is completed

mPOS sends BuyItem message to ITS REST API.

ITS REST sends BuyItemResponse

Operator swipes Credit card

mPOS sends ValidateTender message to ITS REST API
.
If the validation is successful then mPOS sends authorize tender message to authorizer for BalanceDue amount

mPOS sends AddAuthorizedTender message to ITS REST API with information from authorizer

ITS REST sends AddAuthorizedTenderResponse

mPOS sends EndTransaction message to ITS REST API.

ITS REST sends EndTransactionResponse
