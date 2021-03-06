---
title: "“从现有代码文件创建新项目”向导 -&gt;“指定调试配置设置” | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.importwiz.debugsettings"
dev_langs: 
  - "C++"
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# “从现有代码文件创建新项目”向导 -&gt;“指定调试配置设置”
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

使用“从现有代码文件创建新项目”向导的此页，可以指定“调试”配置项目设置。  
  
## 任务列表  
 [如何：通过现有代码创建 C\+\+ 项目](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## UIElement 列表  
 **生成命令行**  
 指定生成新项目的命令行。  例如，输入要用于生成新项目的编译器的名称（加上所有开关和参数）或生成脚本。  如果在**“指定项目设置”**页中选择**“使用外部生成系统”**选项，则将启用此选项；否则此选项将不可用。  
  
 **重新生成命令行**  
 指定重新生成新项目的命令行。  如果在**“指定项目设置”**页中选择**“使用外部生成系统”**选项，则将启用此选项；否则此选项将不可用。  
  
 **清除命令行**  
 指定用于删除支持文件的命令行，这些文件是生成工具为新项目生成的。  如果在**“指定项目设置”**页中选择**“使用外部生成系统”**选项，则将启用此选项；否则此选项将不可用。  
  
 **输出\(用于调试\)**  
 为新项目的“调试”配置指定输出文件的目录路径。  如果在**“指定项目设置”**页中选择**“使用外部生成系统”**选项，则将启用此选项；否则此选项将不可用。  
  
 **预处理器定义\(\/D\)**  
 定义新项目的预处理器符号。  有关更多信息，请参见 [\/D（预处理器定义）](../build/reference/d-preprocessor-definitions.md)。  
  
 **包含搜索路径\(\/I\)**  
 指定要添加到目录列表中的目录路径，编译器将在新项目中搜索这些目录路径，以解析传递给预处理器指令的文件引用。  有关更多信息，请参见 [\/I（附加包含目录）](../build/reference/i-additional-include-directories.md)。  
  
 **强制包含的文件\(\/FI\)**  
 指定在生成新项目时要处理的头文件。  有关更多信息，请参见 [\/FI（命名强制包含文件）](../build/reference/fi-name-forced-include-file.md)。  
  
 **.NET 程序集搜索路径\(\/AI\)**  
 指定目录路径，编译器将在新项目中搜索这些目录路径，以解析传递给预处理器指令的 .NET 程序集引用。  有关更多信息，请参见 [\/AI（指定元数据目录）](../build/reference/ai-specify-metadata-directories.md)。  
  
 **强制使用 .NET 程序集\(\/FU\)**  
 指定在生成新项目时要处理的 .NET 程序集。  有关更多信息，请参见 [\/FU（命名强制 \#using 文件）](../build/reference/fu-name-forced-hash-using-file.md)。  
  
## 请参阅  
 [“从现有代码文件创建新项目”向导 \-\>“指定项目设置”](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)