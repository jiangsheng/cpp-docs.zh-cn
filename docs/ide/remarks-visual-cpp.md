---
title: "&lt;备注&gt;（Visual c + +） |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- remarks
- <remarks>
dev_langs: C++
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 369a8b7a2addaf2fcc39b598b7ce6582c26e1e98
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="ltremarksgt-visual-c"></a>&lt;备注&gt;（Visual c + +）
\<remarks> 标记用于添加有关某个类型的信息，从而补充由 [\<summary>](../ide/summary-visual-cpp.md) 指定的信息。 此信息显示在[对象浏览器](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470)和代码注释 Web 报表中。  
  
## <a name="syntax"></a>语法  
  
```  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>参数  
 `description`  
 对成员的说明。  
  
## <a name="remarks"></a>备注  
 使用 [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) 进行编译可以将文档注释处理到文件中。  
  
## <a name="example"></a>示例  
  
```  
// xml_remarks_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_remarks_tag.dll  
  
using namespace System;  
  
/// <summary>  
/// You may have some primary information about this class.  
/// </summary>  
/// <remarks>  
/// You may have some additional information about this class.  
/// </remarks>  
public ref class MyClass {};  
```  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档](../ide/xml-documentation-visual-cpp.md)