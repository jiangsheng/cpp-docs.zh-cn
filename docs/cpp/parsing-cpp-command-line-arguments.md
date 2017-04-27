---
title: "分析 C++ 命令行自变量 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "引号引起来，命令行参数"
  - "双引号"
  - "命令行分析"
  - "分析、 命令行参数"
  - "启动代码，分析命令行参数"
ms.assetid: e634e733-ac2f-4298-abe2-7e9288c94951
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 分析 C++ 命令行自变量
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 专用**  
  
 在解释操作系统命令行上给出的参数时，Microsoft C/c + + 启动代码将使用以下规则︰  
  
-   参数用空白分隔，空白可以是一个空格或制表符。  
  
-   插入符号 (^) 未被识别为转义符或者分隔符。 该字符完全处理由操作系统的命令行分析器在传递给之前 `argv` 在程序中的数组。  
  
-   由双引号括起来的字符串 ("*字符串*") 被解释为单个参数，而不考虑包含空白。 带引号的字符串可以嵌入在自变量内。  
  
-   双精度的引号前面加上反斜杠 (\\") 被解释为原义双引号字符 （"）。  
  
-   反斜杠按其原义解释，除非它们紧位于双引号之前。  
  
-   如果偶数个反斜杠后跟双引号中, 放置一个反斜杠 `argv` 数组以及每对反斜杠，双引号被解释为字符串分隔符。  
  
-   如果奇数个反斜杠后跟双引号中, 放置一个反斜杠 `argv` 以及每对反斜杠，双引号字符的数组由导致义双引号字符 （"） 放入其余的反斜杠进行"转义" `argv`。  
  
## <a name="example"></a>示例  
 以下程序演示如何命令行参数传递︰  
  
```  
// command_line_arguments.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
int main( int argc,      // Number of strings in array argv  
          char *argv[],   // Array of command-line argument strings  
          char *envp[] )  // Array of environment variable strings  
{  
    int count;  
  
    // Display each command-line argument.  
    cout << "\nCommand-line arguments:\n";  
    for( count = 0; count < argc; count++ )  
         cout << "  argv[" << count << "]   "  
                << argv[count] << "\n";  
}  
```  
  
 下表显示示例输入和预期的输出，演示上述列表中的规则。  
  
### <a name="results-of-parsing-command-lines"></a>分析命令行的结果  
  
|命令行输入|argv[1]|argv [2]|argv [3]|  
|-------------------------|---------------|---------------|---------------|  
|`"abc" d e`|`abc`|`d`|`e`|  
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|  
|`a\\\"b c d`|`a\"b`|`c`|`d`|  
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|  
  
## <a name="end-microsoft-specific"></a>结束 Microsoft 专用  
  
## <a name="see-also"></a>另请参阅  
 [main︰ 程序启动](../cpp/main-program-startup.md)