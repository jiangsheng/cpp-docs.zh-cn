---
title: "编译器错误 C2472 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2472
dev_langs:
- C++
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ed41a3d78ab9652d1e88ceefe29011eb5b2225a4
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2472"></a>编译器错误 C2472
“function”无法在托管代码“message”中生成；请使用 /clr 进行编译以生成混合映像  
  
 当在纯公共语言运行库 (CLR) 环境中使用托管代码不支持的类型时，将出现此错误。 请使用 **/clr** 进行编译以解决该错误。  
  
 **/clr:pure** 和 **/clr:safe** 编译器选项在 Visual Studio 2015 中已弃用。  
  
## <a name="example"></a>示例  
 下面的示例生成 C2472。  
  
```  
// C2472.cpp  
// compile with: /clr:pure  
// C2472 expected  
  
#include <cstdlib>  
  
int main()  
{  
   int * __ptr32 p32;  
   int * __ptr64 p64;  
  
   p32 = (int * __ptr32)malloc(4);  
   p64 = p32;  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [/clr （公共语言运行时编译）](../../build/reference/clr-common-language-runtime-compilation.md)
