### ErrorItem 
Details about errors associated with adding an item that can be
recovered by operator action.
```csharp
public class ErrorItem : RetryableError

{

/// <summary>

/// Item code

/// </summary>

public string ItemCode;

/// <summary>

/// Scan code

/// </summary>

public string ScanCode;

/// <summary>

/// Item description

/// </summary>

public string Description;

/// <summary>

/// Unit price

/// </summary>

[DataMember]

public decimal UnitPrice;

/// <summary>

/// True if item requires authorization ( gift card sale etc )

/// </summary>

public bool ItemAuthorizationRequired;

/// <summary>

/// True if the weight is required

/// </summary>

public bool WeightRequired;

/// <summary>

/// True if the item quantity is required

/// </summary>

public bool QuantityRequired;

/// <summary>

/// True if the item is a price required item

/// </summary>

public bool PriceRequired;

/// <summary>

/// True if the item is not on file

/// </summary>

public bool NotOnFile;

/// <summary>

/// True if the item is a commissioned item

/// </summary>

public bool CommissionedItem;

/// <summary>

/// True if a serial number is required

/// </summary>

public bool SerialNumberRequired;

/// <summary>

/// True if a restocking fee prompt should be made

/// </summary>

public bool HasRestockingFee;

/// <summary>

/// List of restrictions that can be satisfied by the operator

/// </summary>

public RestrictionDetails[] Restrictions;

}
```