---
title: "编译器错误 C3707 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3707
dev_langs:
- C++
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7167ea0df9bc0846de16be40d722c63bfea11c32
ms.contentlocale: zh-cn
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3707"></a>编译器错误 C3707
function： 调度接口方法必须具有一个 dispid  
  
 如果你使用`dispinterface`方法，你必须将其分配`dispid`。 若要修复此错误，分配`dispid`到`dispinterface`方法，例如，通过取消注释`id`在下面的示例方法的特性。 有关详细信息，请参阅属性[调度接口](../../windows/dispinterface.md)和[id](../../windows/id.md)。  
  
 下面的示例生成 C3707:  
  
```  
// C3707.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(name="xx")];  
[dispinterface]  
__interface IEvents : IDispatch  
{  
   HRESULT event1([in] int i);   // C3707  
   // try the following line instead  
   // [id(1)] HRESULT event1([in] int i);  
};  
  
int main() {  
}  
```
