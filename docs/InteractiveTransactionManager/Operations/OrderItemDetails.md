### OrderItemDetails

Details about an order item
```csharp
public class OrderItemDetails
{
/// <summary>

/// Item code in external system (SAP)

/// </summary>

public string ExternalItemCode;

/// <summary>

/// Item code

/// </summary>

public string ItemCode;

/// <summary>

/// Item description

/// </summary>

public string Description;

/// <summary>

/// Item quantity

/// </summary>

public decimal Quantity;

/// <summary>

/// Unit price

/// </summary>

public decimal UnitPrice;

/// <summary>

/// Extended price

/// </summary>

public decimal ExtendedPrice;

/// <summary>

/// Discount amount

/// </summary>

public decimal DiscountAmount;

/// <summary>

/// Total tax amount

/// </summary>

public decimal TaxAmount;

/// <summary>

/// Unit of measure id

/// </summary>

public int UnitOfMessure;

/// <summary>

/// Order status

/// </summary>

public OrderItemStatus Status;

/// <summary>

/// Line number of item in the order

/// </summary>

public int OrderLineNumber;

/// <summary>

/// Line number of item in the basket

/// </summary>

public int BasketLineNumber;

/// <summary>

/// For a returned order item the reason for the return

/// </summary>

public int? ReasonCode;

/// <summary>

/// For a returned order item the reason code description for the return

/// </summary>

public string ReasonCodeDescription;

/// <summary>

/// Total of any fee items

/// </summary>

public decimal FeeTotal;

}
```