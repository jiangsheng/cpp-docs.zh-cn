---
title: "编译器警告（等级 1）C4789 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4789"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4789"
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# 编译器警告（等级 1）C4789
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

缓冲区“identifier”\(大小为 N 字节\)将溢出；M 字节将在偏移 L 时开始写入  
  
 在使用特定 C 运行时 \(CRT\) 函数、传递参数以及执行赋值时针对缓冲区溢出进行警告，以便在编译时知道数据大小。  此警告针对那些可能会避开典型数据大小不匹配检测的情况。  
  
 将编译时已知其长度的数据复制并放入其大小在编译时已知太小、无法容纳数据的数据块时，会出现该警告。  必须通过使用以下 CRT 函数之一的内部形式完成复制：  
  
-   [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)  
  
-   [memset](../../c-runtime-library/reference/memset-wmemset.md)  
  
-   [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)、[wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)  
  
 当使用强制转换使参数数据类型不匹配时，也会出现警告，然后尝试从左值引用进行复制赋值。  
  
 Visual C\+\+ 可能会对不曾执行的代码路径生成此警告。  可以使用 `#pragma` 临时禁用该警告，如此示例中所示：  
  
 `#pragma(push)`  
  
 `#pragma warning ( disable : 4789 )`  
  
 `// unused code that generates compiler warning C4789`  
  
 `#pragma(pop)`  
  
 这可防止 Visual C\+\+ 对该特定代码块生成警告。  `#pragma(push)` 会在 `#pragma warning(disable: 4789)` 更改现有状态之前保留该状态。  `#pragma(pop)` 会还原压入的状态，并移除 `#pragma warning(disable:4789)` 的效果。  有关 C\+\+ 预处理器指令 `#pragma` 的详细信息，请参阅[警告](../../preprocessor/warning.md)以及 [Pragma 指令和 \_\_Pragma 关键字](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)。  
  
## 示例  
 以下示例生成 C4789。  
  
```  
// C4789.cpp  
// compile with: /Oi /W1 /c  
#include <string.h>  
#include <stdio.h>  
  
int main()   
{  
    char a[20];  
    strcpy(a, "0000000000000000000000000\n");   // C4789  
  
    char buf2[20];  
    memset(buf2, 'a', 21);   // C4789  
  
    char c;  
    wchar_t w = 0;  
    memcpy(&c, &w, sizeof(wchar_t));  
}  
```  
  
## 示例  
 以下示例也生成 C4789。  
  
```  
// C4789b.cpp  
// compile with: /W1 /O2 /c  
// processor: x86  
short G;  
  
void main()  
{  
   int * p = (int *)&G;   
   *p = 3;   // C4789 - writes an int through a pointer to short  
}   
```