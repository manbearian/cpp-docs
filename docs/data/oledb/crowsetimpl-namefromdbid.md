---
title: "CRowsetImpl::NameFromDBID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: ["cpp-windows"]
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: ["CRowsetImpl.NameFromDBID", "CRowsetImpl::NameFromDBID"]
dev_langs: ["C++"]
helpviewer_keywords: ["NameFromDBID method"]
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
ms.workload: ["cplusplus", "data-storage"]
---
# CRowsetImpl::NameFromDBID
Extracts a string from a **DBID** and copies it to the `bstr` passed in.  
  
## Syntax  
  
```  
  
      HRESULT CRowsetBaseImpl::NameFromDBID(  
   DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex   
);  
```  
  
#### Parameters  
 *pDBID*  
 [in] A pointer to the **DBID** from which to extract a string.  
  
 `bstr`  
 [in] A [CComBSTR](../../atl/reference/ccombstr-class.md) reference to place a copy of the **DBID** string.  
  
 `bIndex`  
 [in] **true** if an index **DBID**; **false** if a table **DBID**.  
  
## Return Value  
 A standard `HRESULT`. Depending on whether the **DBID** is a table or an index (denoted by `bIndex`), the method will either return **DB_E_NOINDEX** or **DB_E_NOTABLE**.  
  
## Remarks  
 This method is called by the `CRowsetImpl` implementations of [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) and [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md).  
  
## Requirements  
 **Header:** atldb.h  
  
## See Also  
 [CRowsetImpl Class](../../data/oledb/crowsetimpl-class.md)