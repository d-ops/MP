---
layout: default
title: Initial Workflow
nav_order: 1
parent: Sample Workflow
grand_parent: Interactive Transaction Manager
has_children: true
---

### Initial Workflow

mPOS sends Initialize message to ITS REST API.

ITS REST sends ClientDetails response.

mPOS sends SignOn message to ITS REST API.

ITS REST sends EmployeesPostResponse.

mPOS sends StartBasket message to ITS REST API.

ITS REST sends BasketIdentifier Response
