---
title: "is_trivially_move_assignable 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_trivially_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 3f4f27b070a607db4a9ed6929ded346a1be76685
ms.contentlocale: zh-cn
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable 类
测试类型是否具有普通移动赋值运算符。  
  
## <a name="syntax"></a>语法  
  
```
template <class Ty>
struct is_trivially_move_assignable;
```  
  
#### <a name="parameters"></a>参数  
 `Ty`  
 要查询的类型。  
  
## <a name="remarks"></a>备注  
 如果类型 `Ty` 是具有普通移动赋值运算符的类，则类型谓词的实例为 true；否则为 false。  
  
 如果符合以下条件，类 `Ty` 的移动赋值运算符是普通运算符：  
  
 它被隐式提供  
  
 类 `Ty` 没有虚函数  
  
 类 `Ty` 没有虚拟基  
  
 类类型的所有非静态数据成员的类具有普通移动赋值运算符  
  
 类的类型数组的所有非静态数据成员的类具有普通移动赋值运算符  
  
## <a name="requirements"></a>要求  
 **标头：**\<type_traits>  
  
 **命名空间：** std  
  
## <a name="see-also"></a>另请参阅  
 [<type_traits>](../standard-library/type-traits.md)




