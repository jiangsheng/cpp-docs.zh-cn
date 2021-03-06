---
title: "LIB 输入文件 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords: input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f956dedb8be270eb9974fa035d38e7fbb6714499
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="lib-input-files"></a>LIB 输入文件
LIB 所需的输入的文件取决于在其中它的使用的模式下, 表中所示。  
  
|模式|输入|  
|----------|-----------|  
|默认值 （生成或修改库）|COFF 对象 (.obj) 文件，COFF 库 (.lib)，32 位对象模型格式 (OMF) 对象 (.obj) 文件|  
|提取与 /extract، 成员|COFF 库 (.lib)|  
|生成导出文件和导入具有 /DEF 库|模块定义 (.def) 文件、 COFF 对象 (.obj) 文件、 COFF 库 (.lib)、 32 位 OMF 对象 (.obj) 文件|  
  
> [!NOTE]
>  OMF 库创建的 LIB 的 16 位版本不能为 LIB 的 32 位版本的输入。  
  
## <a name="see-also"></a>另请参阅  
 [LIB 概述](../../build/reference/overview-of-lib.md)