---
title: "汇编语言注释 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b93f00aac6151471c1e36b29b2d9f5c3cdbdc1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="assembly-language-comments"></a>汇编语言注释
## <a name="microsoft-specific"></a>Microsoft 专用  
 `__asm` 块中的指令可使用汇编语言注释：  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 由于 C 宏会扩展为单个逻辑行，因此应避免在宏中使用汇编语言注释。 (请参阅[__asm 块定义为 C 宏](../../assembler/inline/defining-asm-blocks-as-c-macros.md)。)`__asm`块也可包含 C 样式注释; 有关详细信息，请参阅[使用 C 或 c + + 在 __asm 块中](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)。  
  
 **结束 Microsoft 专用**  
  
## <a name="see-also"></a>另请参阅  
 [在 __asm 块中使用汇编语言](../../assembler/inline/using-assembly-language-in-asm-blocks.md)