---
title: "&lt;exception&gt; | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <exception>
dev_langs: C++
helpviewer_keywords: exception header
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a7624e80138e2c7feb77b9aa385a40a2b5fe0320
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="ltexceptiongt"></a>&lt;exception&gt;
定义与异常处理相关的若干类型和函数。 异常处理用于系统可从错误中恢复的情形。 它提供了将控制权从函数返回给程序的一种方法。 合并异常处理的目标是提高程序的可靠性，同时提供一种有序地从错误中恢复的方法。  
  
## <a name="syntax"></a>语法  
  
```  
#include <exception>  
  
```  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)|该类型描述指向异常的指针。|  
|[terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)|该类型描述指向适合用作 `terminate_handler` 的函数的指针。|  
|[unexpected_handler](../standard-library/exception-typedefs.md#unexpected_handler)|该类型描述指向适合用作 `unexpected_handler` 的函数的指针。|  
  
### <a name="functions"></a>函数  
  
|||  
|-|-|  
|[current_exception](../standard-library/exception-functions.md#current_exception)|获取指向当前异常的指针。|  
|[get_terminate](../standard-library/exception-functions.md#get_terminate)|获取当前的 `terminate_handler` 函数。|  
|[get_unexpected](../standard-library/exception-functions.md#get_unexpected)|获取当前的 `unexpected_handler` 函数。|  
|[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)|创建保留异常副本的 `exception_ptr` 对象。|  
|[rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)|引发作为参数传递的异常。|  
|[set_terminate](../standard-library/exception-functions.md#set_terminate)|建立程序终止时要调用的新 `terminate_handler`。|  
|[set_unexpected](../standard-library/exception-functions.md#set_unexpected)|建立遇到意外异常时要调用的新 `unexpected_handler`。|  
|[terminate](../standard-library/exception-functions.md#terminate)|调用终止处理程序。|  
|[uncaught_exception](../standard-library/exception-functions.md#uncaught_exception)|仅当引发的异常当前正在处理时返回 **true**。|  
|[unexpected](../standard-library/exception-functions.md#unexpected)|调用意外处理程序。|  
  
### <a name="classes"></a>类  
  
|||  
|-|-|  
|[bad_exception 类](../standard-library/bad-exception-class.md)|该类描述可从 `unexpected_handler` 引发的异常。|  
|[exception 类](../standard-library/exception-class.md)|该类用作某些表达式和 C++ 标准库所引发的所有异常的基类。|  
  
## <a name="see-also"></a>另请参阅  
 [头文件引用](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)

