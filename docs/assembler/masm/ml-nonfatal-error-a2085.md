---
title: "ML 非致命错误 A2085 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2085
dev_langs: C++
helpviewer_keywords: A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d93ec58a7f55a2d875cc07dfbddff103b052f98c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="ml-nonfatal-error-a2085"></a>ML 非致命错误 A2085
**指令或不接受当前 CPU 模式中的注册**  
  
 尝试使用指令、 注册或对当前处理器模式下无效的关键字。  
  
 例如，32 位寄存器要求[.386](../../assembler/masm/dot-386.md)或更高版本。 控制寄存器如 CR0 需要特权模式下[.386P](../../assembler/masm/dot-386p.md)或更高版本。 此错误也会生成有关**NEAR32**， **FAR32**，和**平面**需要的关键字。**386**或更高版本。  
  
## <a name="see-also"></a>另请参阅  
 [ML 错误消息](../../assembler/masm/ml-error-messages.md)