### Store 
```csharp
/// <summary>
/// Identifies aspects of a specific Store within an Enterprise.
/// </summary>

public class Store
{
/// <summary>
/// ConfigPoint for a selling location within the enterprise
/// </summary>

public int ConfigPoint { get; set; }
/// <summary>
/// unique identifier assigned to the selling location within the
enterprise
/// </summary>

public int SellingLocationId { get; internal set; }
/// <summary>
/// A culture name in the format languagecode2-country/regioncode2, such as en-ENU for English.
/// See: System.Globalization.CultureInfo for details.
/// </summary>

public string CultureName { get; internal set; }
/// <summary>
/// A store's geographic position ( not currently used)
/// </summary>

public GeoPosition GeoPosition { get; internal set; }
/// <summary>
/// Indicates whether the Store's current business day is opened or closed.
/// </summary>

[DataMember]

public StoreStatus Status { get; internal set; }

[DataMember]

public string EncryptionSeed { get; internal set; }
}
```