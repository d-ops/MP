### TenderDetails  
```csharp
/// <summary>

/// Details about a tender

/// </summary>

[DataContract]

public class TenderDetails : BasketItemDetails

{

/// <summary>

/// Tender description

/// </summary>

[DataMember]

public string Description;

/// <summary>

/// Tendered amount

/// </summary>

[DataMember]

public decimal Amount;

/// <summary>

/// Tender code

/// </summary>

[DataMember]

public int TenderCode;

/// <summary>

/// Token representing account number

/// </summary>

[DataMember]

public string AccountToken;

/// <summary>

/// OPOS Signature data

/// </summary>

[DataMember]

public string SignatureData;

}
```