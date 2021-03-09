### RestrictionType 

Restriction types that require operator intervention to resolve
```csharp
public enum RestrictionType

{

/// <summary>

/// Operator age check is required ( must request manager approval )

/// </summary>

OperatorAge,

/// <summary>

/// Check of customer age is required

/// </summary>

CustomerAge,

/// <summary>

/// Signature is required

/// </summary>

SignatureRequired,

/// <summary>

/// Item check is required

/// </summary>

ItemCheck

}
```