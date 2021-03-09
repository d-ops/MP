---
layout: default
title: LogToEJ
nav_order: 54
parent: Overview
grand_parent: Interactive Transaction Manager
has_children: true
---
### LogToEJ 

This message is called to allow to the client to perform Electronic
Journal logging. The text to log to the EJ is included in the request.
The client should use this message type to log specific data to the
electronic journal.

**Uri**: /logs

**Http Verb**: POST

**Request body**:
```csharp
public class JournalRequest
{
/// <summary>
/// Message number from FujitsuPOS.ElectronicJournalLogDefinition table
/// </summary>

public int MessageNumber;
/// <summary>
/// Substitution parameters for message
/// </summary>

public string[] Parameters;
}
```