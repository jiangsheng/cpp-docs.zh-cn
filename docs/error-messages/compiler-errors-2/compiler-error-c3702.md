---
title: "编译器错误 C3702 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3702
dev_langs: C++
helpviewer_keywords: C3702
ms.assetid: 14fcc20e-4404-45d7-be54-e4f09332fa5a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a6d41ff2f20caa61126c122b50957037718968d3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3702"></a>编译器错误 C3702
function: ATL 是所必需的 COM 事件  
  
 你试图使用 COM 事件，而不包括必要的 ATL 标头文件。  
  
 下面的示例生成 C3702:  
  
```  
// C3702.cpp  
// uncomment the following line to resolve  
// #define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name=idid, uuid="12341234-1234-1234-1234-123412341234")];  
  
[object]  
__interface IEvents : IUnknown  
{  
   HRESULT event1([in] int i);  
};  
  
[dual]  
__interface IBase  
{  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com)]  
class CEventSrc : public IBase  
{  
   public:  
   __event __interface IEvents;  
  
   HRESULT fireEvents()  
   {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};   // C3702  
  
int main() {  
}  
```