---
title: "编译器错误 C3896 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3896
dev_langs: C++
helpviewer_keywords: C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 37390df0763856c671a078ee2fe4df984bd995d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3896"></a>编译器错误 C3896
member： 不正确的初始值设定项： 只能与 nullptr 初始化此 literal 数据成员  
  
 A[文本](../../windows/literal-cpp-component-extensions.md)数据成员未正确初始化。  请参阅[nullptr](../../windows/nullptr-cpp-component-extensions.md)有关详细信息。  
  
 下面的示例生成 C3896:  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```