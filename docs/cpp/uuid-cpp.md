---
title: "uuid （c + +） |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: uuid_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2a2e7ccf1074393a4f71f5d55155cd7e14b5d9f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="uuid-c"></a>uuid (C++)
**Microsoft 专用**  
  
 编译器将 GUID 附加到使用 `uuid` 特性声明或定义的（仅完整的 COM 对象定义）类或结构中。  
  
## <a name="syntax"></a>语法  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## <a name="remarks"></a>备注  
 `uuid` 特性采用字符串作为其参数。 此字符串命名的普通注册表格式带有或不带 GUID **{}**分隔符。 例如:   
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 此特性可应用于重新声明。 这允许系统标头提供接口定义，如**IUnknown**，和其他标头 （如 COMDEF 中的重新声明。H) 提供 GUID。  
  
 关键字[__uuidof](../cpp/uuidof-operator.md)可以应用检索 GUID 附加到的用户定义的类型的常量。  
  
 **结束 Microsoft 专用**  
  
## <a name="see-also"></a>另请参阅  
 [__declspec](../cpp/declspec.md)   
 [关键字](../cpp/keywords-cpp.md)