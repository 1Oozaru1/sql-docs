---
title: "BeginTransaction Element (XMLA) | Microsoft Docs"
ms.custom: ""
ms.date: "06/13/2017"
ms.prod: "sql-server-2014"
ms.reviewer: ""
ms.technology: 
  - "analysis-services"
  - "docset-sql-devref"
ms.topic: "reference"
api_name: 
  - "BeginTransaction Element"
api_location: 
  - "http://schemas.microsoft.com/analysisservices/2003/engine"
topic_type: 
  - "apiref"
f1_keywords: 
  - "urn:schemas-microsoft-com:xml-analysis#BeginTransaction"
  - "microsoft.xml.analysis.begintransaction"
  - "http://schemas.microsoft.com/analysisservices/2003/engine#BeginTransaction"
helpviewer_keywords: 
  - "BeginTransaction command"
ms.assetid: fca122fc-b57c-4ba6-849b-ca8c93cf64e9
author: minewiskan
ms.author: owend
manager: craigg
---
# BeginTransaction Element (XMLA)
  Begins a transaction on the current session with an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
## Syntax  
  
```xml  
  
<Command>  
   <BeginTransaction />  
</Command>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-n: Optional element that can occur more than once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Command](../xml-elements-properties/command-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The `BeginTransaction` command begins an active transaction on the current session. If an active transaction already exists, the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance increments the reference count of transactions for the current session. If not, the instance will begin a new transaction and set the reference count for the current session to 1. If an active transaction is explicitly specified using the `BeginTransaction` command, all subsequent commands are executed inside the explicitly specified transaction.  
  
 When the current session is ended and the reference count for transactions is higher than zero, all active transactions are rolled back.  
  
 If there are no explicitly specified active transactions on the current session, every command issued on the current session is executed inside an implicitly defined transaction. The implicit transaction is committed if the command succeeds, or rolled back if the command fails.  
  
## See Also  
 [Cancel Element &#40;XMLA&#41;](cancel-element-xmla.md)   
 [CommitTransaction Element &#40;XMLA&#41;](committransaction-element-xmla.md)   
 [RollbackTransaction Element &#40;XMLA&#41;](rollbacktransaction-element-xmla.md)   
 [Commands &#40;XMLA&#41;](xml-elements-commands.md)  
  
  
