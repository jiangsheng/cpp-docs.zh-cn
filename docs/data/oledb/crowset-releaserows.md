---
title: "CRowset::ReleaseRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ReleaseRows"
  - "CRowset::ReleaseRows"
  - "ATL::CRowset<TAccessor>::ReleaseRows"
  - "CRowset<TAccessor>.ReleaseRows"
  - "CRowset.ReleaseRows"
  - "ATL.CRowset.ReleaseRows"
  - "ATL.CRowset<TAccessor>.ReleaseRows"
  - "CRowset<TAccessor>::ReleaseRows"
  - "ATL::CRowset::ReleaseRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseRows 方法"
ms.assetid: fa7254f5-566f-4754-bdf7-d0874256926f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::ReleaseRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

调用释放当前行句柄的 [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx)。  
  
## 语法  
  
```  
  
HRESULT ReleaseRows( ) throw( );  
  
```  
  
## 返回值  
 标准 `HRESULT`。  
  
## 要求  
 **标头:** atldbcli.h  
  
## 请参阅  
 [CRowset 类](../../data/oledb/crowset-class.md)