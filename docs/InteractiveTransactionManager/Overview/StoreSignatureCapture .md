---
layout: default
title: StoreSignatureCapture
nav_order: 42
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### StoreSignatureCapture 

This message is called to store signature capture image for a
transaction. The signature capture image is in the OPOS signature
capture format. A line number must be present in the request to
associate the signature data with. Signatures may only be associated
with Tenders.

**Uri**: /baskets/{id}/tenders/{linenumber}

**Http Verb**: POST

**Request body**:

String representation of the OPOS signature capture data
