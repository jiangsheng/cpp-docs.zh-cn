---
title: "条件运算符：? : | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "?:"
  - "?"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "? : 运算符"
  - "条件运算符"
ms.assetid: 88643ee8-7100-4f86-880a-705ec22b6271
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 条件运算符：? :
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 语法  
  
```  
  
expression ? expression : expression  
```  
  
## 备注  
 条件运算符 \(**? :**\) 是一个三元运算符（采用三个操作数）。  条件运算符按以下方式运行：  
  
-   第一个操作数隐式转换为 `bool`。  计算该操作数，并在继续前完成所有副作用。  
  
-   如果第一个操作数的计算结果为 **true** \(1\)，则计算第二个操作数。  
  
-   如果第一个操作数的计算结果为 **false** \(0\)，则计算第三个操作数。  
  
 条件运算符的结果是操作数（无论是第二个还是第三个）的计算结果。  只有最后两个操作数之一在条件表达式中计算。  
  
 条件表达式具有从右到左的关联性。  第一个操作数必须是整数或指针类型。  以下规则适用于第二个和第三个操作数：  
  
-   如果两个操作数是相同的类型，则结果也是该类型。  
  
-   如果两个操作数都是算术或枚举类型，则执行常用算术转换（在[算术转换](../misc/arithmetic-conversions.md)中有述）来将它们转换为通用类型。  
  
-   如果两个操作数都是指针类型，或者一个是指针类型，另一个是计算结果为 0 的常量表达式，则执行指针转换来将它们转换为通用类型。  
  
-   如果两个操作数都是引用类型，则执行引用转换来将它们转换为通用类型。  
  
-   如果两个操作数都是 void 类型，则通用类型是 void 类型。  
  
-   如果两个操作数是相同的用户定义类型，则通用类型也是该类型。  
  
-   如果操作数是不同的类型，而且至少有一个操作数是用户定义类型，则使用语言规则来确定通用类型。  （请参阅下面的警告。）  
  
 前面列表中没有的第二个和第三个操作数的任意组合都是非法的。  结果的类型是通用类型，如果第二个和第三个操作数是同一类型且都是左值，则结果为左值。  
  
> [!WARNING]
>  如果第二个和第三个操作数的类型不相同，则会按 C\+\+ 标准中的指定调用复杂类型转换规则。  这些转换可能会导致意外行为，包括构造和析构临时对象。  为此，我们强烈建议：\(1\) 避免将用户定义的类型用作带条件运算符的操作数；\(2\) 如果确实要使用用户定义的类型，务必将每个操作数显式转换为通用类型。  
  
## 示例  
  
```  
// expre_Expressions_with_the_Conditional_Operator.cpp  
// compile with: /EHsc  
// Demonstrate conditional operator  
#include <iostream>  
using namespace std;  
int main() {  
   int i = 1, j = 2;  
   cout << ( i > j ? i : j ) << " is greater." << endl;  
}  
```  
  
## 请参阅  
 [C\+\+ 运算符](../misc/cpp-operators.md)   
 [C\+\+ 运算符优先级和关联性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [条件表达式运算符](../c-language/conditional-expression-operator.md)