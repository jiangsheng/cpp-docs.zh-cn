---
title: "vararg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.vararg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vararg attribute"
ms.assetid: 20fc3244-18e9-411c-990e-d5b4fa29a570
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# vararg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定函数采用的参数数目可变。  
  
## 语法  
  
```  
  
[vararg]  
  
```  
  
## 备注  
 **vararg** C\+\+ 特性具有与 [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) MIDL 属性相同。  
  
## 示例  
 下面的代码演示 **vararg**的使用:  
  
```  
// cpp_attr_ref_vararg.cpp  
// compile with: /LD  
#include "unknwn.h"  
#include "oaidl.h"  
[module(name="MyLibrary")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface X : public IUnknown   
{  
   [vararg] HRESULT Button([in, satype(VARIANT)]SAFEARRAY *psa);  
};  
```  
  
## 要求  
  
### 属性上下文  
  
|||  
|-|-|  
|**适用对象**|接口方法|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|无|  
  
 有关属性上下文的更多信息，请参见 [属性上下文](../windows/attribute-contexts.md)。  
  
## 请参阅  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/zh-cn/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)