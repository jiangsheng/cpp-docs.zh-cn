---
title: "CInterfaceArray 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
dev_langs: C++
helpviewer_keywords: CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5a06fe0f7fab05b6b73856fa3f326f1c54d4f55c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="cinterfacearray-class"></a>CInterfaceArray 类
构造的 COM 接口指针的数组时，此类提供有用的方法。  
  
## <a name="syntax"></a>语法  
  
```
template <class I, const IID* piid=& __uuidof(I)>  
class CInterfaceArray : 
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>参数  
 `I`  
 COM 接口，指定要存储的指针的类型。  
  
 `piid`  
 指向 IID 的`I`。  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|接口数组构造函数。|  
  
## <a name="remarks"></a>备注  
 此类提供一个构造函数和派生的方法用于创建 COM 接口指针的数组。 使用[CInterfaceList](../../atl/reference/cinterfacelist-class.md)需要列表时。  
  
 有关详细信息，请参阅[ATL 集合类](../../atl/atl-collection-classes.md)。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## <a name="requirements"></a>要求  
 **标头：** atlcoll.h  
  
##  <a name="cinterfacearray"></a>CInterfaceArray::CInterfaceArray  
 构造函数。  
  
```
CInterfaceArray() throw();
```  
  
### <a name="remarks"></a>备注  
 初始化智能指针数组。  
  
## <a name="see-also"></a>另请参阅  
 [CAtlArray 类](../../atl/reference/catlarray-class.md)   
 [CComQIPtr 类](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits 类](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [类概述](../../atl/atl-class-overview.md)
