---
title: "一维数组 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- brackets [ ]
- brackets [ ], arrays
- one-dimensional arrays
- arrays [C++], one-dimensional
- square brackets [ ]
- square brackets [ ], arrays
- subscript expressions
ms.assetid: e28536e5-3b77-46b5-97fd-9b938c771816
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea3d4c2461579fcafc4f9ff7ba5071572229c640
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="one-dimensional-arrays"></a>一维数组
后跟用方括号 ([ ]) 括起的表达式的后缀表达式是数组对象元素的下标表示形式。 下标表达式表示在表示为以下形式时位于超出 postfix-expression 的 expression 位置的地址的值  
  
```  
  
postfix-expression  
[  
expression  
]  
  
```  
  
 通常，postfix-expression 表示的值是一个指针值（如数组标识符），而 expression 是一个整数值。 但是，从语法上来说，只需要一个表达式是指针类型，另一个表达式是整型。 因此整数值可以位于 postfix-expression 位置，指针值可以位于 expression 的方括号中或“下标”位置。 例如，以下代码是合法的：  
  
```  
// one_dimensional_arrays.c  
int sum, *ptr, a[10];  
int main() {  
   ptr = a;  
   sum = 4[ptr];  
}  
```  
  
 下标表达式通常用于引用数组元素，但您可以将下标应用于任何指针。 无论值的顺序如何，expression 必须用方括号 ([ ]) 括起来。  
  
 通过将整数值添加到指针值，然后将间接寻址运算符 (\*) 应用于结果，可以计算下标表达式。 （有关间接寻址运算符的讨论，请参阅[间接寻址运算符和 Address-of 运算符](../c-language/indirection-and-address-of-operators.md)。）实际上，对于一维数组，假定 `a` 是指针，`b` 是整数，则以下四个表达式等效：  
  
```  
a[b]  
*(a + b)  
*(b + a)  
b[a]  
```  
  
 根据加法运算符的转换规则（在[相加运算符](../c-language/c-additive-operators.md)中提供），可通过将整数值乘以指针寻址的类型的长度来将整数值转换为地址偏移量。  
  
 例如，假定标识符 `line` 引用 `int` 值的数组。 以下过程用于计算下标表达式 `line[ i ]`：  
  
1.  将整数值 `i` 乘以定义为 `int` 项的长度的字节数。 `i` 的转换值表示 `i` `int` 位置。  
  
2.  此转换值将添加到原始指针值 (`line`) 以生成从 `line` 偏移 `i` `int` 个位置的地址。  
  
3.  间接寻址运算符将应用于此新地址。 结果是位于该位置（直观地说，就是 `line [ i ]`）的数组元素的值。  
  
 下标表达式 `line[0]` 表示行的第一个元素的值，因为 `line` 表示的地址的偏移量为 0。 同样，表达式（如 `line[5]`）引用了从行偏移 5 个位置的元素，或数组的第 6 个元素。  
  
## <a name="see-also"></a>另请参阅  
 [下标运算符：](../cpp/subscript-operator.md)