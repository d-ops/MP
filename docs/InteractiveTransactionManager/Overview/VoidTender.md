---
layout: default
title: VoidTender
nav_order: 43
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---

### VoidTender 

This message is called to void an authorized tender. The reversal must
be authorized by the 3^rd^ party system prior to making this call. The
line number of the tender to be voided is specified in the request. The
authorization reversal response data from the provider must be included
in the request. Updated totals information and updated tenders list is
returned in the response.

Optionally the request may include a reason code.

**Uri**: /baskets/{id}/tenders/{linenumber}

**Http Verb**: POST(cannot be DELETE as DELETE does not have a request
body)

**Request body**: See VoidRequest above

**Response Body**: See TenderUpdatesResponse above.
