---
title: "make_unsigned 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::make_unsigned
dev_langs:
- C++
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: fdd04e8b2b235e9711036fbb66f9ac0ed8a99e75
ms.contentlocale: zh-cn
ms.lasthandoff: 10/03/2017

---
# <a name="makeunsigned-class"></a>make_unsigned 类
设置类型或大小大于或等于类型的无符号的最小类型。  
  
## <a name="syntax"></a>语法  
  
```
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```  
  
#### <a name="parameters"></a>参数  
  
|参数|说明|  
|---------------|-----------------|  
|`T`|要修改的类型。|  
  
## <a name="remarks"></a>备注  
 如果 `is_unsigned<T>` 为 true，则类型修饰符的实例保留修改后的类型 `T`。 否则，它就是适用于 `sizeof (T) <= sizeof (ST)` 的最小的带符号类型 `ST`。  
  
## <a name="requirements"></a>要求  
 **标头：**\<type_traits>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [<type_traits>](../standard-library/type-traits.md)




