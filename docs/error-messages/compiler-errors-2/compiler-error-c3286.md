---
title: "编译器错误 C3286 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3286
dev_langs:
- C++
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 551d5136cec63b968ce7b9711b06d8c7b509d9c8
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3286"></a>编译器错误 C3286
“specifier”：迭代变量不能包含任何存储类说明符  
  
 请参阅[(NOTINBUILD) 存储类说明符](http://msdn.microsoft.com/en-us/10b3d22d-cb40-450b-994b-08cf9a211b6c)有关详细信息。  
  
 请参阅[对于每一个，在](../../dotnet/for-each-in.md)有关详细信息。  
  
## <a name="example"></a>示例  
 以下示例生成 C3286：  
  
```  
// C3286.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p = { 1, 2, 3 };  
   for each (static int i in p) {}   // C3286   
   for each (int j in p) {}   // OK  
}  
```
