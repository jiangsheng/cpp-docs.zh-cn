---
title: "编译器错误 C2009 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2009
dev_langs:
- C++
helpviewer_keywords:
- C2009
ms.assetid: fe9d94ed-20a5-4d83-b9c4-60ee69d2f30a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2bbae441d7b4c9e57a4080dd643f6563eed6c48e
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2009"></a>编译器错误 C2009
宏形式 “identifier” 重复使用  
  
 宏定义的形参列表不止一次使用的标识符。 宏的参数列表中的标识符必须是唯一的。  
  
## <a name="example"></a>示例  
 下面的示例生成 C2009:  
  
```  
// C2009.cpp  
#include <stdio.h>  
  
#define macro1(a,a) (a*a)   // C2009  
  
int main()   
{  
    printf_s("%d\n", macro1(2));  
}  
```  
  
## <a name="example"></a>示例  
 可能的解决方法：  
  
```  
// C2009b.cpp  
#include <stdio.h>  
  
#define macro2(a)   (a*a)   
#define macro3(a,b) (a*b)  
  
int main()   
{  
    printf_s("%d\n", macro2(2));  
    printf_s("%d\n", macro3(2,4));  
}  
```
