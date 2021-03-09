### ItemUpdates 

Updates made to the basket as a result of adding an item
```csharp
public class ItemUpdates
{
/// <summary>
/// New items added to the basket - will only be more than one if linked
or set items were associated
/// </summary>

public ItemDetails[] NewItems;
/// <summary>
/// Existing items whose net selling price changes as a result ( i.e.
prorated taxes / discounts changed )
/// </summary>

public ItemDetails[] ChangedItems;
/// <summary>
/// Suggested items
/// </summary>

public SuggestedItem[] SuggestedItems;
/// <summary>
/// Tax details
/// </summary>

public TaxDetails[] Taxes;
/// <summary>
/// Discount details
/// </summary>

public DiscountDetails[] Discounts;
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
/// </summary>

public decimal DiscountTotal;
}
```