---
title: "编译器错误 C2065 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 81686df4727ab2b3d5af749174a42016e8443e70
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2065"></a>编译器错误 C2065
“identifier”：未声明的标识符  
  
 必须先在声明中指定变量的类型，然后才能使用。 必须先在声明或原型中指定函数使用的参数，然后才能使用该函数。  
  
 可能的原因：  
  
1.  标识符名称拼写错误。  
  
2.  标识符使用了错误的大写和小写字母。  
  
3.  字符串常量后缺少右引号。  
  
4.  您正在编译用 C 运行时，调试版本声明中的 c + + 标准库迭代器变量`for`循环，并尝试使用该迭代器变量的作用域之外`for`循环。 编译用 C 运行库的调试版本的 c + + 标准库代码意味着[/zc: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)。  请参阅[调试迭代器支持](../../standard-library/debug-iterator-support.md)有关详细信息。  
  
5.  你可能会调用你的生成环境中当前并不支持的 SDK 头文件中的函数。  
  
6.  省略必要包含文件，尤其是如果定义了 `VC_EXTRALEAN`、`WIN32_LEAN_AND_MEAN` 或 `WIN32_EXTRA_LEAN` 时。 这些符号从 windows.h 和 afxv_w32.h 中排除某些头文件，以便加快编译速度。 （查看 windows.h 和 afxv_w32.h，了解排除内容的最新描述。）  
  
7.  不正确的命名空间范围。 例如，若要解析 C++ 标准库函数和非完全限定的运算符，必须使用 `using` 指令指定 `std` 命名空间。 无法编译下面的示例，因为 `using` 指令已被注释掉且在 `std` 命名空间中定义了 `cout`：  
  
## <a name="example"></a>示例  
 以下示例生成 C2065，并演示如何修复此错误。  
  
```  
// C2065.cpp  
// compile with: /EHsc  
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
   cout << "Hello" << endl;   // C2065  
  
   // Or try the following line instead  
   std::cout << "Hello" << std::endl;  
}  
```  
  
## <a name="example"></a>示例  
 调用泛型函数时，如果不能从所使用的参数中推导预期类型参数，编译器将报告错误。 有关详细信息，请参阅[泛型函数 (C + + /cli CLI)](../../windows/generic-functions-cpp-cli.md)。  
  
 以下示例生成 C2065，并演示如何修复此错误。  
  
```  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
   G<int>(10);   // OK - fix with a specific type argument  
}  
```  
  
## <a name="example"></a>示例  
 此错误还可能来自于为 Visual C++ 2005 执行的编译器一致性工作：Visual C++ 特性的参数检查。  
  
 以下示例生成 C2065，并演示如何修复此错误。  
  
```  
// C2065_c.cpp  
// compile with: /c  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```