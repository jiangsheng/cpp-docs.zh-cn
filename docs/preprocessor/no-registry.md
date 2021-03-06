---
title: "no_registry |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_registry
dev_langs: C++
helpviewer_keywords: no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 347cdd89a8d8c3014a02708c91df3292275f4e3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="noregistry"></a>no_registry
`no_registry` 告知编译器不在寄存器中搜索使用 `#import` 导入的类型库。  
  
## <a name="syntax"></a>语法  
  
```  
  
#import filename no_registry  
```  
  
#### <a name="parameters"></a>参数  
 *filename*  
 类型库。  
  
## <a name="remarks"></a>备注  
 如果在包含目录中找不到引用的类型库，编译将失败，即使在注册表中的类型库。  `no_registry`将传播到隐式导入与其他类型库`auto_search`。  
  
 编译器绝不会在寄存器中搜索由文件名指定并直接传递到 `#import` 的类型库。  
  
 指定 `auto_search` 后，将使用初始 `#import` 的 `no_registry` 设置生成额外的 `#import`（如果初始 `#import` 指令是 `no_registry`，则 `auto_search` 生成的 `#import` 也是 `no_registry`。）  
  
 `no_registry`如果你想要导入交叉引用的类型库，而没有在注册表中查找文件的旧版本的编译器的风险，很有用。  `no_registry`也是有用的如果未注册类型库。  
  
## <a name="see-also"></a>另请参阅  
 [#import 属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import 指令](../preprocessor/hash-import-directive-cpp.md)