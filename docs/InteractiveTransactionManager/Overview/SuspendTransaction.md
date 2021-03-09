---
layout: default
title: SuspendTransaction
nav_order: 46
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### SuspendTransaction 

This message is sent as the final message in the transaction to suspend
the transaction to the server database so that it can be resumed and
completed. Completion will include rescanning problem items (not on
file, age restricted, price required, quantity required, weight required
etc.) and tendering out the transaction.

**Uri**: /baskets/{id}

**Http Verb**: post

**Request Body**:
```csharp
public class TerminateRequest
{
/// <summary>
/// Available reasons for termination
/// </summary>
public enum TerminationType{
Suspend = 0,
Void,
End
}
/// <summary>
/// Selected termination reason
/// </summary>

public TerminationType ReasonType;
/// <summary>
/// Optional reason code
/// </summary>

public int? ReasonCode;
/// <summary>
/// Optional email address to which the receipt should be emailed
/// </summary>

public string EmailAddress;
}
```
ReasonType = TerminationType.Suspend

**Response Body**:
```csharp
/// <summary>
/// Response to a TerminateRequest
/// </summary>

public class TerminateRequestResponse : ManagerResponseData
{
/// <summary>
/// Authorized items : these must be voided before a void or suspend of the transaction is performed
/// </summary>

public ItemDetails[] AuthorizedItems;
/// <summary>
/// Authorized tenders : these must be voided before a void or suspend of the transaction is performed
/// </summary>

public TenderDetails[] AuthorizedTenders;
/// <summary>
/// Receipt data if the request was successful
/// </summary>

public string ReceiptData;
}
```
**Example**:
```json
{"AuthorizedItems":null,"AuthorizedTenders":null,
"ReceiptData":"<SignedFormattedData
xmlns=""><FormattedData Version="2.0"><ReceiptImage
Width="42"><ReceiptLine Alignment="Center"><Field
Text="Market Place"></Field></ReceiptLine><ReceiptLine
Alignment="Center"><Field Text="Fujitsu America
Inc"></Field></ReceiptLine><ReceiptLine
Alignment="Center"><Field
Text=""></Field></ReceiptLine><ReceiptLine
Alignment="Center"><Field
Text="Durham-MainSt-NC"></Field></ReceiptLine><ReceiptLine
Alignment="Center"><Field Text="100 Main
Street"></Field></ReceiptLine><ReceiptLine
Alignment="Center"><Field Text="Durham"></Field><Field
Text=", "></Field><Field Text="NC"></Field><Field
Text=" "></Field><Field
Text="27707"></Field></ReceiptLine><ReceiptLine
Alignment="Center"><Field Text="("></Field><Field
Text="555"></Field><Field Text=")"></Field><Field
Text=" "></Field><Field
Text="5550002"></Field></ReceiptLine><ReceiptLine><Field
Text="__________________________________________"></Field></ReceiptLine>
<ReceiptLine
Alignment="Center" ConditionalPrintType="1"><Field
Text="***** Duplicate *****"><PrintControl
DoubleWide="1"
DoubleHigh="1"></PrintControl></Field></ReceiptLine><LineFeed
Lines="1"></LineFeed><ReceiptLine
Alignment="Center"><Field Text="****** Void Immediate
******"></Field></ReceiptLine><LineFeed
Lines="1"></LineFeed><ReceiptLine><Field
Text="__________________________________________"></Field></ReceiptLine>
<LineFeed
Lines="1"></LineFeed><ReceiptLine><Field
Text="Store:"></Field><Field Text=" "></Field><Field
Text="1022"></Field><Field Text=" "></Field><Field
Text="Register:"></Field><Field Text="
"></Field><Field Text="0100"></Field><Field Text="
"></Field><Field Text="Tran:"></Field><Field Text="
"></Field><Field
Text="0002"></Field></ReceiptLine><ReceiptLine><Field
Text="Oper:"></Field><Field Text=" "></Field><Field
Text="123"></Field><Field Text=" "></Field><Field
Text="2/25/2015 5:23:06 PM"></Field></ReceiptLine><LineFeed
Lines="1"></LineFeed><BarCode Symbology="ITF"
Height="1000" Width="7000" Alignment="Center"
TextPosition="Below" Rotation="Normal"
CheckDigit="12000"
Data="102210000020001022515008"></BarCode><LineFeed
Lines="3"></LineFeed><Cut></Cut></ReceiptImage><PrinterDefaults
Width="42" SidewaysMaxLines="17" SidewaysMaxChars="40"
MapMode="METRIC"
PrinterStation="RECEIPT"></PrinterDefaults></FormattedData><Signature
xmlns="http://www.w3.org/2000/09/xmldsig#"><SignedInfo>
<CanonicalizationMethod
Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315">
</CanonicalizationMethod><SignatureMethod
Algorithm="http://www.w3.org/2000/09/xmldsig#rsa-sha1">
</SignatureMethod><Reference
URI=""><Transforms><Transform
Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature">
</Transform></Transforms><DigestMethod
Algorithm="http://www.w3.org/2000/09/xmldsig#sha1">
</DigestMethod><DigestValue>Ei0q+QHyutHcY/j/YDq7bHr+jWo=</DigestValue>
</Reference></SignedInfo>
<SignatureValue>koqsuOQuvoEn0LEDJnoNtzuw51YfwHE4LpqZmwlvr5ZvYj2vHzqmrXb3I5k
RGZWHbYJ3oRU/KFqmYQ7WjWR+6nz7gWZAEvdgNBzO3TVQGNXaz9y0BMyOo3kdTccsGjQZ3ijaiS
pcvz65o39/BD8pGktMy8LQgl4zx6tj7UPmk9pELlzMUfQFvozG7BFEgZd8EQeSfPs08S3T1ZspW
2ZahC+U+SNreNQvYppGo16wDHI/kW4kL1AweQ9BbYdrNEa/hnRTrFAbm0BlWaruW3rgzVLJNrEc
B6YW4V0FgO8KYCz9rgMdfSJnLegSOAoiXTSb072kfJhI7+14GScdz4p7qQ==
</SignatureValue></Signature></SignedFormattedData>"}
```