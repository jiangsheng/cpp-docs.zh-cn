---
title: "编译器错误 C3799 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3799
dev_langs: C++
helpviewer_keywords: C3799
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2f26afc9573cc12b2f13c83911188e677ce134a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3799"></a>编译器错误 C3799
索引的属性不能具有空的参数列表  
  
未正确声明索引的属性。 有关详细信息，请参阅[如何： 使用属性在 C + + /cli CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)。  
  
## <a name="example"></a>示例  
下面的示例生成 C3799，并演示如何修复此错误。  
  
```cpp  
// C3799.cpp  
// compile with: /clr /c  
ref struct C {  
   property int default[] {   // C3799  
   // try the following line instead  
   // property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
```