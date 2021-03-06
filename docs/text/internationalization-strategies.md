---
title: "国际化策略 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 944ba06bd7b3d81abb2ab431494096f9ade77574
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="internationalization-strategies"></a>国际化策略
根据您的目标操作系统和市场，你有几个国际化策略：  
  
-   你的应用程序使用 Unicode，并因此运行 Windows 2000 和 Windows NT 中，但不是能在 Windows 95 或 Windows 98。  
  
     使用 Unicode 特有的功能和所有字符宽度都为 16 位 （尽管出于特殊目的，可以在程序的某些部分中使用 ANSI 字符）。 C 运行库提供仅 Unicode 编程函数、 宏和数据类型。 MFC 是完全支持 Unicode。  
  
-   你的应用程序使用 MBCS，并且可以在任何 Win32 平台上运行。  
  
     使用特定于 MBCS 的功能。 字符串可以包含单字节字符和 / 或双字节字符。 C 运行库提供仅 MBCS 编程函数、 宏和数据类型。 MFC 是完全 MBCS 启用。  
  
-   为完成的可移植性编写你的应用程序的源代码 — 通过使用符号重新编译**_UNICODE**或符号**_MBCS**定义，您可以生成使用的版本。 有关详细信息，请参阅[Tchar.h 中的一般文本映射](../text/generic-text-mappings-in-tchar-h.md)。  
  
-   你的应用程序可用于一个包装库缺少 Windows 95、 Windows 98 和 Windows ME 上的 Unicode 函数，如本文中其中一个[设计一个在两个 Windows 98 和 Windows 2000 运行的单个 Unicode 应用](http://go.microsoft.com/fwlink/p/?LinkId=250770)。 包装库也有用于商业目的。  
  
     将使用完全可移植的 C 运行时函数、 宏和数据类型。 MFC 的灵活性支持所有这些策略。  
  
 这些主题的其余部分专注于编写可以生成为 Unicode 或 MBCS 的完全可移植代码。  
  
## <a name="see-also"></a>另请参阅  
 [Unicode 和 MBCS](../text/unicode-and-mbcs.md)   
 [区域设置和代码页](../text/locales-and-code-pages.md)