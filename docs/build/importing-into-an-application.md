---
title: "导入到应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], importing
- importing DLLs [C++], applications
- applications [C++], importing into
ms.assetid: 9d646466-e12e-4710-8ad9-c819c0375fcc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2c52ed2188f758ca6b46a6d2ccc880077878d4a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="importing-into-an-application"></a>导入到应用程序中
你可以将函数导入应用程序使用两种方法：  
  
-   使用关键字**__declspec （dllimport)**函数定义在主应用程序中  
  
-   使用模块定义 (.def) 文件以及**__declspec （dllimport)**  
  
## <a name="what-do-you-want-to-do"></a>你希望做什么？  
  
-   [导入使用 __declspec （dllimport） 的应用程序](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [使用 __declspec （dllimport） 导入函数调用](../build/importing-function-calls-using-declspec-dllimport.md)  
  
-   [导入数据使用 __declspec （dllimport）](../build/importing-data-using-declspec-dllimport.md)  
  
-   [导入使用 DEF 文件](../build/importing-using-def-files.md)  
  
## <a name="see-also"></a>另请参阅  
 [导入和导出](../build/importing-and-exporting.md)