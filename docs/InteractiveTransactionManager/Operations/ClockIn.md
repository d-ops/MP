---
layout: default
title: ClockIn  
nav_order: 3
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# ClockIn
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This is used to clock in an operator. The message will include an
operator ID and password. The operator id must be a valid UMS user.

## Uri
/employees/{id}/clockin

## Http Verb
POST

## Request body

String password;

## Response body data

Same as sign on above -- EmployeesPostResponse.
