---
title: "编译器警告 （等级 1） C4154 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4154
dev_langs: C++
helpviewer_keywords: C4154
ms.assetid: 4511afeb-e893-4cc6-83b6-4c7a0477f76b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 71a76d17b7ce52a46f3d8b0ce7c075b10b69fef9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4154"></a>编译器警告 （等级 1） C4154
删除数组表达式;提供的指针转换  
  
 不能使用`delete`上一个数组，因此编译器将数组转换为指针。  
  
## <a name="example"></a>示例  
  
```  
// C4154.cpp  
// compile with: /c /W1  
int main() {  
   int array[ 10 ];  
   delete array;   // C4154 can't delete stack object  
  
   int *parray2 = new int [10];  
   int (&array2)[10] = (int(&)[10]) parray2;  
   delete [] array2;   // C4154  
  
   // try the following line instead  
   delete [] &array2;  
}  
```