---
title: "BSCMAKE 参考 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".bsc 文件, 生成"
  - "浏览信息文件 (.bsc), 生成"
  - "浏览窗口"
  - "bsc 文件, 生成"
  - "BSCMAKE"
  - "BSCMAKE, 参考"
  - "Microsoft 浏览信息维护实用工具"
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# BSCMAKE 参考
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!WARNING]
>  虽然安装 Visual Studio 时仍会安装 BSCMAKE，但 IDE 将不再使用它。  从 Visual Studio 2008 起，浏览信息和符号信息自动存储在解决方案文件夹的 SQL Server .sdf 文件中。  
  
 Microsoft 浏览信息维护实用工具 \(BSCMAKE.EXE\) 从编译期间创建的 .sbr 文件生成浏览信息文件 \(.bsc\)。  在对象浏览器中查看浏览信息文件。  有关对象浏览器的信息，请参阅[在对象浏览器中导航](http://msdn.microsoft.com/zh-cn/53eb91aa-08c6-4299-8e3c-a877ae8d0c55)。  
  
 生成程序时，可以使用 BSCMAKE 生成浏览信息文件，以自动为你的程序创建浏览信息文件。  如果在 Visual C\+\+ 开发环境中创建浏览信息文件，则不需要知道如何运行 BSCMAKE。  但是，你可能需要阅读本主题以了解可用的选项。  
  
 如果在开发环境外部生成程序，则仍可以创建一个可在该环境中检查的自定义 .bsc。  对编译期间创建 .sbr 文件运行 BSCMAKE。  
  
> [!NOTE]
>  你只能从 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 命令提示符启动此工具。  不能从系统命令提示符或从文件资源管理器启动此工具。  
  
 本节包括下列主题：  
  
-   [生成浏览信息文件：概述](../../build/reference/building-browse-information-files-overview.md)  
  
-   [生成 .bsc 文件](../../build/reference/building-a-dot-bsc-file.md)  
  
-   [BSCMAKE 命令行](../../build/reference/bscmake-command-line.md)  
  
-   [BSCMAKE 命令行](../../build/reference/bscmake-command-file-response-file.md)  
  
-   [BSCMAKE 选项](../../build/reference/bscmake-options.md)  
  
-   [BSCMAKE 退出代码](../../build/reference/bscmake-exit-codes.md)  
  
## 请参阅  
 [C\/C\+\+ 生成工具](../../build/reference/c-cpp-build-tools.md)