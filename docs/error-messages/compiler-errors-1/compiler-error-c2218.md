---
title: "编译器错误 C2218 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2218
dev_langs:
- C++
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3ca2e431fdfeff3c9dc957bee46f84cfd2c04162
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2218"></a>编译器错误 C2218
“__vectorcall”不能和“/arch:IA32”一起使用  
  
 `__vectorcall` 调用约定仅受到包括流式处理 SIMD 扩展 2 (SSE2) 和更高版本的 x86 和 x64 处理器上的本机代码的支持。 有关详细信息，请参阅[__vectorcall](../../cpp/vectorcall.md)。  
  
 若要修复此错误，请将编译器选项更改为目标 SSE2、AVX 或 AVX2 指令集的。 有关详细信息，请参阅 [/arch (x86)](../../build/reference/arch-x86.md)。
