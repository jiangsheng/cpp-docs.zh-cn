---
title: "iostreams 约定 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
caps.latest.revision: 10
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
ms.openlocfilehash: 247f9948c6f22e7d24c47966a398d1b33e054f45
ms.lasthandoff: 02/24/2017

---
# <a name="iostreams-conventions"></a>iostreams 约定
iostreams 标头支持文本和编码格式间的转换，以及支持输入和输出到外部文件：  
  
|||  
|-|-|  
|[\<fstream>](../standard-library/fstream.md)|[\<iomanip>](../standard-library/iomanip.md)|  
|[\<ios>](../standard-library/ios.md)|[\<iosfwd>](../standard-library/iosfwd.md)|  
|[\<iostream>](../standard-library/iostream.md)|[\<istream>](../standard-library/istream.md)|  
|[\<ostream>](../standard-library/ostream.md)|[\<sstream>](../standard-library/sstream.md)|  
|[\<streambuf>](../standard-library/streambuf.md)|[\<strstream>](../standard-library/strstream.md)|  
  
 iostreams 最简单的用法仅要求包含标头 [\<iostream>](../standard-library/iostream.md)。 然后可从 [cin](../standard-library/iostream.md#cin) 或 [wcin](../standard-library/iostream.md#wcin) 提取值来读取标准输入。 其操作规则在 [basic_istream 类](../standard-library/basic-istream-class.md) 的说明中有所概述。 还可将值插入 [cout](../standard-library/iostream.md#cout) 或 [wcout](../standard-library/iostream.md#wcout) 来写入标准输出。 其操作规则在 [basic_ostream 类](../standard-library/basic-ostream-class.md) 的说明中有所概述。 提取符和插入符的常规格式控件由 [basic_ios 类](../standard-library/basic-ios-class.md) 管理。 借助提取和插入对象来处理此格式信息是多个操控程序的范围。  
  
 你可使用 [\<fstream>](../standard-library/fstream.md) 中声明的类，对按名称打开的文件执行相同的 iostreams 操作。 若要在类 [basic_string 类](../standard-library/basic-string-class.md) 的 iostreams 和对象间进行转换，请使用 [\<sstream>](../standard-library/sstream.md) 中声明的类。 若要对 C 字符串执行相同操作，请使用 [\<strstream>](../standard-library/strstream.md) 中声明的类。  
  
 剩余标头提供支持服务，通常只与 iostreams 类的最高级用户直接相关。  
  
## <a name="see-also"></a>另请参阅  
 [C++ 标准库概述](../standard-library/cpp-standard-library-overview.md)   
 [iostream 编程](../standard-library/iostream-programming.md)   
 [C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)

