---
layout: default
title: ManagerApproval
nav_order: 51
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### ManagerApproval 

This function is used to provide manager approval functionality. If the
currently signed on employee does not have authorization to perform a
given function then a Manager Approval must be performed prior to having
a function returning Success. Any employee that has authorization may
perform the manager approval. A Manger Approval is only valid for the
next action e.g. the action that failed must be repeated after signing
on the manager. The manager will automatically be signed off by the next
action.

**Uri**: /employees/{id}/managersignon

**Http Verb**: POST

**Request body**:

String password;

**Response body data**: See EmployeesPostResponse above.
