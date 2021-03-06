---
title: "sync_per_container 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
dev_langs:
- C++
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 8628d2866fa4a180975cde1f0ea161378afc6d50
ms.contentlocale: zh-cn
ms.lasthandoff: 10/03/2017

---
# <a name="syncpercontainer-class"></a>sync_per_container 类
描述为每个筛选器对象提供单独的缓存对象的[同步筛选](../standard-library/allocators-header.md) 。  
  
## <a name="syntax"></a>语法  
  
```
template <class Cache>  
class sync_per_container
 : public Cache
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|`Cache`|与同步筛选器相关联的缓存类型。 它可以是 [cache_chunklist](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md) 或 [cache_suballoc](../standard-library/cache-suballoc-class.md)。|  
  
### <a name="member-functions"></a>成员函数  
  
|||  
|-|-|  
|[equals](#equals)|比较两个缓存是否相等。|  
  
## <a name="requirements"></a>要求  
 **标头：**\<allocators>  
  
 **命名空间：** stdext  
  
##  <a name="equals"></a>  sync_per_container::equals  
 比较两个缓存是否相等。  
  
```
bool equals(const sync_per_container<Cache>& Other) const;
```  
  
### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|`Cache`|同步筛选器的缓存对象。|  
|`Other`|要用于比较是否相等的缓存对象。|  
  
### <a name="return-value"></a>返回值  
 此成员函数总是返回 `false`。  
  
### <a name="remarks"></a>备注  
  
## <a name="see-also"></a>另请参阅  
 [\<allocators>](../standard-library/allocators-header.md)




