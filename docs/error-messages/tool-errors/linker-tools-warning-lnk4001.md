---
title: "链接器工具警告 LNK4001 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4001
dev_langs: C++
helpviewer_keywords: LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cfb73e0c62a49fe5190103987277483d29af71fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4001"></a>链接器工具警告 LNK4001
未指定; 的对象文件使用库  
  
 链接器已传递一个或多个.lib 文件，但不是含.obj 文件。  
  
 链接器不能访问它就可以访问在.obj 文件中的.lib 文件中的信息，因为此警告意味着需要显式指定其他链接器选项。 例如，你可能需要指定[/计算机](../../build/reference/machine-specify-target-platform.md)， [/out](../../build/reference/out-output-file-name.md)，或[/ENTRY](../../build/reference/entry-entry-point-symbol.md)选项。