---
title: "本地 (MASM) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Local
dev_langs: C++
helpviewer_keywords: LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 60dac02a5bf08f7ced2fbb8adb46cc558cbfe44b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="local-masm"></a>LOCAL (MASM)
中的第一个指令，宏，内部**本地**定义宏的每个实例是唯一的标签。  
  
## <a name="syntax"></a>语法  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## <a name="remarks"></a>备注  
 在第二个指令，在过程定义中 (**PROC**)，**本地**创建存在过程的持续时间内的基于堆栈的变量。 *标签*可能是简单变量或一个数组，包含*计数*元素。  
  
## <a name="see-also"></a>另请参阅  
 [指令参考](../../assembler/masm/directives-reference.md)