---
layout: default
title: SignOn  
nav_order: 1
parent: Operations
grand_parent: Interactive Transaction Manager
---
# SignOn
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
---

This message is sent to sign on an operator. The message will include an
operator ID and password. The operator id must be a valid UMS user.

The sign on will persist the STS token in the local memory cache. A HTTP
message handler will be used to associate the STS token with the current
thread on incoming messages.

Signing On must proceed the starting of a basket. Lookup will be
supported before SignOn.

## Uri 
/employees/{id}/signon

## Http Verb
POST

## Request body

String password;

## Response body data
```csharp
/// <summary>
/// Response to an employees post message
/// </summary>

public class EmployeesPostResponse
{
/// <summary>
/// Sign on result
/// </summary>

public AuthenticationResult Result;
/// <summary>
/// Details about authorized operator
/// </summary>

public Operator OperatorDetails;
}
```
If the sign on succeeds or if a password change is required then
HttpStatusCode.OK will be returned. Any other sign on errors will result
in HttpStatusCode.Unauthorized.

## Example
```json
{"Result":0,"OperatorDetails":{"$id":"1","Id":"111",
"WorkerId":"10210003","CultureName":"en-US"}}
```