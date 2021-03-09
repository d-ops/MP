---
layout: default
title: ClockOut
nav_order: 4
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### ClockOut 

This is used to clock out an operator. The message will include an
operator ID and password. The operator id must be a valid UMS user.

**Uri**: /employees/{id}/clockout

**Http Verb**: POST

**Request body**:

String password;

**Response body data**:

Same as sign on above -- EmployeesPostResponse.
