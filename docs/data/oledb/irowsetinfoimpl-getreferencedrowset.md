---
title: "Irowsetinfoimpl:: Getreferencedrowset |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
dev_langs: C++
helpviewer_keywords: GetReferencedRowset method
ms.assetid: 94d2155c-9da0-4c19-a37c-bc35716359fd
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5901c87b5f3287da6c663402b7e7776158db85e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetinfoimplgetreferencedrowset"></a>IRowsetInfoImpl::GetReferencedRowset
到书签所应用到的行集返回的接口指针。  
  
## <a name="syntax"></a>语法  
  
```  
  
      STDMETHOD ( GetReferencedRowset )(  
   DBORDINAL iOrdinal,  
   REFIID riid,  
   IUnknown** ppReferencedRowset   
);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[IRowsetInfo::GetReferencedRowset](https://msdn.microsoft.com/en-us/library/ms721145.aspx)中*OLE DB 程序员参考*。 *IOrdinal*参数必须是书签列。  
  
## <a name="requirements"></a>要求  
 **标头：** atldb.h  
  
## <a name="see-also"></a>另请参阅  
 [IRowsetInfoImpl 类](../../data/oledb/irowsetinfoimpl-class.md)   
 [Irowsetinfoimpl:: Getspecification](../../data/oledb/irowsetinfoimpl-getspecification.md)   
 [IRowsetInfoImpl::GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)