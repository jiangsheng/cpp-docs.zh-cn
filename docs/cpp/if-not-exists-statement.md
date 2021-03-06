---
title: "__if_not_exists 语句 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __if_not_exists_cpp
dev_langs: C++
helpviewer_keywords: __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5bd11ed833b54082d7ea2a394bdd4cad3c3e1321
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="ifnotexists-statement"></a>__if_not_exists 语句
`__if_not_exists` 语句测试指定的标识符是否存在。 如果该标识符不存在，则执行指定的语句块。  
  
## <a name="syntax"></a>语法  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|`identifier`|要测试其存在性的标识符。|  
|`statements`|一个或多个时要执行的语句`identifier`不存在。|  
  
## <a name="remarks"></a>备注  
  
> [!CAUTION]
>  若要实现最可靠的结果，请在以下约束条件下使用 `__if_not_exists` 语句。  
  
-   只将 `__if_not_exists` 语句应用于简单类型而不是模板。  
  
-   将 `__if_not_exists` 语句应用于类的内部或外部的标识符。 不要将 `__if_not_exists` 语句应用于局部变量。  
  
-   仅在函数的主体中使用 `__if_not_exists` 语句。 在函数主体的外部，`__if_not_exists` 语句仅能测试完全定义的类型。  
  
-   在测试重载函数时，不能测试特定形式的重载。  
  
 对补充`__if_not_exists`语句是[__if_exists](../cpp/if-exists-statement.md)语句。  
  
## <a name="example"></a>示例  
 有关如何使用的示例`__if_not_exists`，请参阅[__if_exists 语句](../cpp/if-exists-statement.md)。  
  
## <a name="see-also"></a>另请参阅  
 [选择语句](../cpp/selection-statements-cpp.md)   
 [关键字](../cpp/keywords-cpp.md)   
 [__if_exists 语句](../cpp/if-exists-statement.md)