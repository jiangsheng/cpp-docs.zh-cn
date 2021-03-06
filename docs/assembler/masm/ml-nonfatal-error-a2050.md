---
title: "ML Nonfatal Error A2050 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2050"
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**不允许的物理或 BCD 数字**  
  
 浮点 \(实际\) 除了充当数据 \(BCD\)初始值设定项外，数字或 \- 二个十六进制常数使用了。  
  
 发生的操作之一:  
  
-   添加或 BCD 在表达式。  
  
-   除了 [DWORD](../../assembler/masm/dword.md)、 [QWORD](../../assembler/masm/qword.md)或 [TBYTE](../../assembler/masm/tbyte.md)之外，添加用于初始化指令。  
  
-   除了 `TBYTE`外， BCD 用于初始化指令。  
  
## 请参阅  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)