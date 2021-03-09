### AuthenticationResult 

All possible return codes of authentication
```csharp
public enum AuthenticationResult
{
/// <summary>
/// A user authenticated succesfully.
/// </summary>

Success,

/// <summary>
/// An unexpected error occured during authentication.
/// </summary>

SignonFailed,

/// <summary>
/// Too many failed attempts to sign on.
/// </summary>

RetryCountExceeded,

/// <summary>
/// A password is expired.
/// </summary>

PasswordExpired,

/// <summary>
/// A password change required.
/// </summary>

PasswordChangeRequired,

/// <summary>
/// A password is invalid.
/// </summary>

InvalidPassword,

/// <summary>
/// User that is trying to sign in is not found.
/// </summary>

UnknownOperator,

/// <summary>
/// Too many failed attempts of manager override to sign on.
/// </summary>

OvrdRetryCountExceeded,

/// <summary>
/// A user who tries to log in is already terminated or not yet hired.
/// </summary>

InvalidEmployee,

/// <summary>
/// User exists but password is not assigned yet.
/// </summary>

NoPasswordAssigned
}
```
