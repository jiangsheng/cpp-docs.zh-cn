---
title: "文件转换概述 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- file translation [C++], about file translation
- translation [C++]
- translation phases
- files [C++], translation
- programs [C++], lexical conventions of
- preprocessing translation phase
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 37b10254ca101bcf19aff3c84abac4a122f242eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="overview-of-file-translation"></a>文件转换概述
C++ 程序（如 C 程序）由一个或多个文件组成。 这些文件中的每个文件按以下概念顺序进行翻译（实际顺序遵循“似同”规则：必须进行翻译，就似同已执行这些步骤一样）：  
  
1.  词法切分。 字符映射以及三元组处理、行拼接和切分在此翻译阶段执行。  
  
2.  预处理。 此翻译阶段将引入引用的辅助源文件`#include`指令，处理"stringizing"和"字符化"指令，并执行标记粘贴和宏扩展 (请参阅[预处理器指令](../preprocessor/preprocessor-directives.md)在*预处理器参考*有关详细信息)。 预处理阶段的结果是一系列共同用于定义“翻译单元”的标记。  
  
     预处理器指令总是以数字符号开头 (**#**) 字符 （即，在行上的第一个非空白字符必须是数字符号）。 一个给定行上只能出现一个预处理器指令。 例如：  
  
    ```  
    #include <iostream>  // Include text of iostream in   
                         //  translation unit.  
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty   
                         //  text string).  
    ```  
  
3.  代码生成。 此翻译阶段使用在预处理阶段生成的标记来生成对象代码。  
  
     在此阶段中，将执行源代码的语法和语义检查。  
  
 请参阅[翻译阶段](../preprocessor/phases-of-translation.md)中*预处理器参考*有关详细信息。  
  
 C++ 预处理器是 ANSI C 预处理器的严格超集，但在某些实例中，C++ 预处理器与 ANSI C 预处理器不同。 以下列表介绍了 ANSI C 和 C++ 预处理器之间的多个差异：  
  
-   支持单行注释。 请参阅[注释](../cpp/comments-cpp.md)有关详细信息。  
  
-   一个预定义的宏， **__cplusplus**，仅为 c + + 定义。 请参阅[预定义的宏](../preprocessor/predefined-macros.md)中*预处理器参考*有关详细信息。  
  
-   C 预处理器无法识别 c + + 运算符： **。\***，  **-> \*** ，和`::`。 请参阅[运算符](../cpp/cpp-built-in-operators-precedence-and-associativity.md)和[表达式](../cpp/expressions-cpp.md)，有关运算符的详细信息。  
  
## <a name="see-also"></a>另请参阅  
 [词法约定](../cpp/lexical-conventions.md)