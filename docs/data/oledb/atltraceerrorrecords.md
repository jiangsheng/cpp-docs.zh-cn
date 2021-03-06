---
title: "AtlTraceErrorRecords |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
dev_langs: C++
helpviewer_keywords: AtlTraceErrorRecords function
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 696d00e32ebf692d8155b93247f3ca83b0bb2b08
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="atltraceerrorrecords"></a>AtlTraceErrorRecords
如果返回错误，则转储到转储设备的 OLE DB 错误记录信息。  
  
## <a name="syntax"></a>语法  
  
```  
  
      inline void AtlTraceErrorRecords(   
   HRESULT hrErr = S_OK    
);  
```  
  
#### <a name="parameters"></a>参数  
 `hErr`  
 [in]`HRESULT` OLE DB 使用者模板成员函数返回。  
  
## <a name="remarks"></a>备注  
 如果`hErr`不`S_OK`，`AtlTraceErrorRecords`转储到转储设备的 OLE DB 错误记录信息 (**调试**选项卡的输出窗口或文件)。 错误记录信息，可从提供程序中获得，对于每个错误记录条目包括行号、 源、 说明、 帮助文件、 上下文和 GUID。 `AtlTraceErrorRecords`转储只在调试版本中的此信息。 在发布版本，它是空的存根出进行了优化。  
  
## <a name="requirements"></a>要求  
 **标头:** atldbcli.h  
  
## <a name="see-also"></a>另请参阅  
 [宏和全局函数 OLE DB 使用者模板](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo 类](../../data/oledb/cdberrorinfo-class.md)