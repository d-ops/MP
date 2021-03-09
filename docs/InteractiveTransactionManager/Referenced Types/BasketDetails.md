---
layout: default
title: BasketDetails
parent: Referenced Types
grand_parent: Interactive Transaction Manager
has_children: true
---
### BasketDetails 
```csharp
/// <summary>
/// Details about a basket
/// </summary>

public class BasketDetails : BasketIdentifier
{

/// <summary>
/// Basket line items
/// </summary>

public ItemDetails[] Items;
/// <summary>
/// Tax details
/// </summary>

public TaxDetails[] Taxes;
/// <summary>
/// Discount details
/// </summary>

public DiscountDetails[] Discounts;
/// <summary>
/// Tender details
/// </summary>

public TenderDetails[] Tenders;
/// <summary>
/// Total extended amount of items
/// </summary>

public decimal SubTotal;
/// <summary>
/// Total tax amount
/// </summary>

public decimal TaxTotal;
/// <summary>
/// Total discount amount
/// </summar>

public decimal DiscountTotal;
/// <summary>
/// Total tendered amount
/// </summary>

public decimal TenderTotal;
}
```