---
title: "字符串化运算符 (#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "# 预处理器运算符"
  - "参数 [C++], 转换为字符串"
  - "宏 [C++], 将参数转换为字符串"
  - "预处理器"
  - "预处理器, 运算符"
  - "字符串, 将宏参数转换为"
  - "字符串化运算符"
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 字符串化运算符 (#)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

数字符号或“字符串化”运算符 \(**\#**\) 将宏参数转换为字符串而不扩展参数定义。  它只用于采用参数的宏。  如果它在宏定义中位于形参之前，则由宏调用传递的实参将用引号引起来并被视为字符串。  字符串随后替换宏定义中的字符串化运算符和形参的组合的每个匹配项。  
  
> [!NOTE]
>  不再支持对 ANSI C 标准的 Microsoft C（6.0 版和早期版本）扩展，该扩展之前扩展了出现在字符串和字符常量内的扩展的宏形参。  应使用字符串化 \(**\#**\) 运算符来重新编写依赖此扩展的代码。  
  
 在实参的第一个标记前且紧跟实参的最后一个标记的空格将被忽略。  在生成的字符串中，将实参标记之间的所有空格减少到单一空格。  因此，如果注释出现在实参的两个标记之间，则将其减少为单个空格。  生成的字符串自动与仅由空格分隔的任何相邻的字符串连接。  
  
 此外，如果参数内的一个字符在字符串中使用时，通常需要转义序列（例如，引号 **"**）或反斜杠（**\\** 字符），必要的转义反斜杠会自动插入到该字符前面。  
  
 Visual C\+\+ 字符串化运算符可能不会在所有情况下像预期那样执行；有关详细信息，请参阅 [16.3.2 \# 运算符](../misc/16-3-2-the-hash-operator.md)。  
  
## 示例  
 以下示例显示一个包含字符串化运算符的宏定义和一个调用该宏的主函数：  
  
 在预处理期间将扩展此类调用，并将生成以下编码：  
  
```  
int main() {  
   printf_s( "In quotes in the printf function call\n" "\n" );  
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );  
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );  
}  
```  
  
```  
// stringizer.cpp  
#include <stdio.h>  
#define stringer( x ) printf_s( #x "\n" )  
int main() {  
   stringer( In quotes in the printf function call );   
   stringer( "In quotes when printed to the screen" );     
   stringer( "This: \"  prints an escaped double quote" );  
}  
```  
  
  **In quotes in the printf function call**  
**"In quotes when printed to the screen"**  
**"This: \\"  prints an escaped double quote"**   
## 示例  
 以下示例说明如何扩展宏参数：  
  
```  
// stringizer_2.cpp  
// compile with: /E  
#define F abc  
#define B def  
#define FB(arg) #arg  
#define FB1(arg) FB(arg)  
FB(F B)  
FB1(F B)  
```  
  
## 请参阅  
 [预处理器运算符](../preprocessor/preprocessor-operators.md)