---
title: "unary_delegate_noreturn (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::unary_delegate_noreturn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unary_delegate_noreturn 函数 [STL/CLR]"
ms.assetid: 3c3fb143-f60f-4e28-a66b-690e3a7b2f9b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# unary_delegate_noreturn (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

genereic 类描述返回 `void`的一参数委托。  使用该指定委托根据其参数类型。  
  
## 语法  
  
```  
generic<typename Arg>  
    delegate void unary_delegate_noreturn(Arg);  
```  
  
#### 参数  
 Arg  
 参数类型。  
  
## 备注  
 genereic 描述委托返回 `void`的一参数函数。  
  
 请注意：  
  
 `unary_delegare_noreturn<int> Fun1;`  
  
 `unary_delegare_noreturn<int> Fun2;`  
  
 `Fun1` 和 `Fun2` 类型是同义词，那么，当进行针对：  
  
 `delegate void Fun1(int);`  
  
 `delegate void Fun2(int);`  
  
 它们不是同一类型。  
  
## 示例  
  
```  
// cliext_unary_delegate_noreturn.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
void hash_val(wchar_t val)   
    {   
    System::Console::WriteLine("hash({0}) = {1}",   
       val, (val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    myhash(L'a');   
    myhash(L'b');   
    return (0);   
    }  
  
```  
  
  **hash\(a\) \= 5**  
**hash\(b\) \= 22**   
## 要求  
 **头文件:** \<cliext\/functional\>  
  
 **命名空间:** cliext  
  
## 请参阅  
 [binary\_delegate](../dotnet/binary-delegate-stl-clr.md)   
 [binary\_delegate\_noreturn](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary\_delegate](../dotnet/unary-delegate-stl-clr.md)