---
title: "编译器警告（等级 4）C4680 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4680"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4680"
ms.assetid: 6e043f4c-c601-4b77-8130-920cff1d912e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 编译器警告（等级 4）C4680
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“class”: coclass 不指定默认接口  
  
 没有为标记有 [coclass](../../windows/coclass.md) 特性的类指定 [default](../../windows/default-cpp.md) 接口。  为了使对象有用，该对象必须实现接口。  
  
 下面的示例生成 C4680：  
  
```  
// C4680.cpp  
// compile with: /W4  
#include <windows.h>  
[module(name="MyModule")];  
  
[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface1  
{  
   HRESULT f1();  
};  
  
[ object, uuid(37331a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface2  
{  
   HRESULT f1();  
};  
  
// to resolve C4680, specify a source interface also  
// for example, default(IMyIface1, IMyface2)  
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f), default(IMyIface1), source(IMyIface1) ]  
class CMyClass : public IMyIface1  
{   // C4680  
};  
  
int main()  
{  
}  
```