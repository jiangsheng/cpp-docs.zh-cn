---
title: "is_nothrow_move_constructible 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_nothrow_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_move_constructible
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: b679a66c19f98cde98fcd134445e1fcea3d12f3e
ms.contentlocale: zh-cn
ms.lasthandoff: 10/03/2017

---
# <a name="isnothrowmoveconstructible-class"></a>is_nothrow_move_constructible 类
测试类型是否具有 **nothrow** 移动构造函数。  
  
## <a name="syntax"></a>语法  
  
```
template <class Ty>
struct is_nothrow_move_constructible;
```  
  
#### <a name="parameters"></a>参数  
 `Ty`  
 要查询的类型。  
  
## <a name="remarks"></a>备注  
 如果类型 `Ty` 具有 nothrow 移动构造函数，则类型谓词的实例将保持为 true，否则保持为 false。  
  
## <a name="requirements"></a>要求  
 **标头：**\<type_traits>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [<type_traits>](../standard-library/type-traits.md)





