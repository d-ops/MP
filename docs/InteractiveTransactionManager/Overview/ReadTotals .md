---
layout: default
title: ReadTotals
nav_order: 49
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### ReadTotals  

This message is called to read hard totals. Optionally, totals can be
zeroed after reading. A receipt is returned in the response that can be
displayed showing the totals.

To read the totals:

**Uri**: /clients/totals

**Http Verb**: GET

**Response Body**: XML totals formatted as a string

To read and clear totals:

**Uri**: /clients/totals

**Http Verb**: DELETE

**Response Body**: XML totals formatted as a string
