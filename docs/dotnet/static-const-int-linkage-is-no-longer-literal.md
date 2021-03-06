---
title: "静态 Const Int 链接不再是文本 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- literal attribute [C++]
- constants, declaring
- integral constant expressions
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d2d4e955df4982ba2077098adc7bd47506b42239
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="static-const-int-linkage-is-no-longer-literal"></a>静态 Const Int 链接不再是文本的
常量的类成员的声明已从托管扩展中的 c + + 更改为 Visual c + +。  
  
 尽管`static const`整型成员仍受支持，其链接属性已更改。 其以前的链接特性现在放置在整型成员。 例如，考虑下面的托管扩展类：  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 此代码生成字段 （请注意文本属性） 的以下基础 CIL 属性：  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 虽然这仍编译在新语法中：  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 它不再发出文本属性，并因此不被视为常量 CLR 运行时：  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 为了具有相同的语言间文本属性，该声明应更改到新的受支持`literal`，如下所示，数据成员  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## <a name="see-also"></a>另请参阅  
 [在类或接口中的成员声明 (C + + /cli CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [文本](../windows/literal-cpp-component-extensions.md)