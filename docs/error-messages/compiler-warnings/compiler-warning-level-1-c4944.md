---
title: "编译器警告 （等级 1） C4944 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4944
dev_langs:
- C++
helpviewer_keywords:
- C4944
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: c145a7157fdd0936eeb63aaff4a545f8de13b17c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4944"></a>编译器警告（等级 1）C4944
“symbol”：无法从“assembly1”导入符号，因为当前范围内已存在“symbol”  
  
 在源代码文件中定义了符号，然后 #using 语句引用了也已定义该符号的程序集。 程序集中的符号将被忽略。  
  
## <a name="example"></a>示例  
 下面的示例使用一个名为 ClassA 类型创建了一个组件。  
  
```  
// C4944.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
## <a name="example"></a>示例  
 以下示例生成 C4944。  
  
```  
// C4944b.cpp  
// compile with: /clr /W1  
class ClassA {  
public:  
   int u;  
};  
  
#using "C4944.dll"   // C4944 ClassA also defined C4944.dll  
  
int main() {  
   ClassA * x = new ClassA();  
   x->u = 9;  
   System::Console::WriteLine(x->u);  
}  
```
