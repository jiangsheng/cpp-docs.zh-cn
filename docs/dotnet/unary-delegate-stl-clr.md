---
title: "unary_delegate (STL/CLR) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::unary_delegate
dev_langs: C++
helpviewer_keywords: unary_delegate function [STL/CLR]
ms.assetid: b3ee253c-98e8-466e-a272-505e47aed061
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 50a59472b2aa2873cf1efe00741f3ddfd98f0e5e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="unarydelegate-stlclr"></a>unary_delegate (STL/CLR)
Genereic 类描述一个单参数的委托。 使用它指定根据其自变量和返回类型的委托。  
  
## <a name="syntax"></a>语法  
  
```  
generic<typename Arg,  
    typename Result>  
    delegate Result unary_delegate(Arg);  
```  
  
#### <a name="parameters"></a>参数  
 Arg  
 参数类型。  
  
 结果  
 返回类型。  
  
## <a name="remarks"></a>备注  
 Genereic 委托介绍了一个自变量的函数。  
  
 请注意，对于：  
  
 `unary_delegare<int, int> Fun1;`  
  
 `unary_delegare<int, int> Fun2;`  
  
 类型`Fun1`和`Fun2`是同义词，而为：  
  
 `delegate int Fun1(int);`  
  
 `delegate int Fun2(int);`  
  
 它们不是同一类型。  
  
## <a name="example"></a>示例  
  
```  
// cliext_unary_delegate.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
int hash_val(wchar_t val)   
    {   
    return ((val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate<wchar_t, int> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
hash(L'a') = 5  
hash(L'b') = 22  
```  
  
## <a name="requirements"></a>要求  
 **标头：** \<功能 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>另请参阅  
 [binary_delegate (STL/CLR)](../dotnet/binary-delegate-stl-clr.md)   
 [binary_delegate_noreturn (STL/CLR)](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary_delegate_noreturn (STL/CLR)](../dotnet/unary-delegate-noreturn-stl-clr.md)