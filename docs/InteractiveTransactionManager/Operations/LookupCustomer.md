---
layout: default
title: LookupCustomer
nav_order: 10
parent: Operations
grand_parent: Interactive Transaction Manager
has_children: true
---
# LookupCustomer 
{: .no_toc }
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
This method can also be used to lookup customer details.

## Uri

/customers/customerid/{id}

Or

/customers/loyaltyid/{id}

Or

/customers/email/{id}

Or

/customers/name/{lastname}

Or

/customers/phonenumber/{id}

## Http Verb
GET

## Response Body

Array of CustomerInformation

## Example
```json
[{"CustomerNumber":"6100000011","LoyaltyNumber":"4100000000123",
"CallingCode":null,"AreaCode":"415","PhoneNumber":"4152221111",
"CustomerName":"John
Harrison","Address":"75 Geary StrnApt#165","City":"SanFrancisco",
"State":"CA","PostCode":"94103","Country":"USA",
"EmailAddress":"john@homemail.com"}]
```