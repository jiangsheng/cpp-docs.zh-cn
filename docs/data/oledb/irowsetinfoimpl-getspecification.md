---
title: "Irowsetinfoimpl:: Getspecification |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetInfoImpl::GetSpecification
- ATL.IRowsetInfoImpl.GetSpecification
- IRowsetInfoImpl.GetSpecification
- GetSpecification
- ATL::IRowsetInfoImpl::GetSpecification
dev_langs: C++
helpviewer_keywords: GetSpecification method
ms.assetid: 8e14289d-9cca-4df7-a9e0-f4ef03c61e30
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 012f845cd47bca6008cdc493651cf17bb1745466
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetinfoimplgetspecification"></a>IRowsetInfoImpl::GetSpecification
返回创建下一个行集合的对象 （命令或会话） 上的接口指针。  
  
## <a name="syntax"></a>语法  
  
```  
  
      STDMETHOD ( GetSpecification )(  
   REFIID riid,  
   IUnknown** ppSpecification   
);  
```  
  
#### <a name="parameters"></a>参数  
 请参阅[IRowsetInfo::GetSpecification](https://msdn.microsoft.com/en-us/library/ms716746.aspx)中*OLE DB 程序员参考*。  
  
## <a name="remarks"></a>备注  
 使用此方法与[IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)从数据源对象中检索属性。  
  
## <a name="requirements"></a>要求  
 **标头：** atldb.h  
  
## <a name="see-also"></a>另请参阅  
 [IRowsetInfoImpl 类](../../data/oledb/irowsetinfoimpl-class.md)   
 [Irowsetinfoimpl:: Getreferencedrowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)   
 [IRowsetInfoImpl::GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)