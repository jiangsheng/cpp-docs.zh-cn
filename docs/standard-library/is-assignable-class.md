---
title: "is_assignable 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_assignable
dev_langs: C++
helpviewer_keywords: is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7c255203b0cb0515d3a46b42bf8813078fcca70c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="isassignable-class"></a>is_assignable 类
测试 `From` 类型的值是否可以分配给 `To` 类型。  
  
## <a name="syntax"></a>语法  
  
```
template <class To, class From>  
struct is_assignable;
```  
  
#### <a name="parameters"></a>参数  
 到  
 接收赋值的对象的类型。  
  
 从  
 提供值的对象的类型。  
  
## <a name="remarks"></a>备注  
 未计算的表达式 `declval<To>() = declval<From>()` 必须具有正确格式。 `From` 和 `To` 都必须是完整类型、`void` 或具有未知边界的数组。  
  
## <a name="requirements"></a>要求  
 **标头：**\<type_traits>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [<type_traits>](../standard-library/type-traits.md)



