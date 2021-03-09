### TaxDetails 

Details about a tax
```csharp
public class TaxDetails : BasketItemDetails
{
/// <summary>
/// Tax description
/// </summary>

public string Description;
/// <summary>
/// Tax amount
/// </summary>

public decimal Amount;
/// <summary>
/// True if the tax is a VAT
/// </summary>

public bool IsVAT;
/// <summary>
/// Associated tax authority id
/// </summary>

public int AuthorityId;
/// <summary>
/// Associated tax code
/// </summary>

public int Id;
}
```