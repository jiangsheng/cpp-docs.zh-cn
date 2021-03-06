---
title: "常规属性（Linux C++ 项目）| Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56c800a9-3df9-4196-87b2-81adb00e4767
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.UseOfSTL
ms.openlocfilehash: 4de08a00ddedf1eec97d1872646a986e09c22547
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="general-properties-linux-c"></a>常规属性 (Linux C++)

属性 | 描述 | 选项
--- | ---| ---
输出目录 | 指定输出文件目录的相对路径；可以包含环境变量。
中间目录 | 指定中间文件目录的相对路径；可以包含环境变量。
Target Name | 指定此项目将生成的文件名。
目标扩展名 | 指定此项目将生成的文件扩展名。 （例如，.a）
清除时要删除的扩展名 | 分号分隔的通配符规范，指定在清除或重新生成时要删除中间目录中的哪些文件。
生成日志文件 | 指定启用生成日志时要写入的生成日志文件。
平台工具集 | 指定用于生成当前配置的工具集；如果未设置，则将使用默认工具集
远程生成计算机 | 要用于远程生成、部署和调试的目标计算机或设备。
远程生成根目录 | 指定远程计算机或设备上目录的路径。
远程生成项目目录 | 指定远程计算机或设备上项目的目录路径。
配置类型 | 指定此配置生成的输出类型。 | **动态库 (.so)** - 动态库 (.so)<br>**静态库 (.a)** - 静态库 (.a)<br>**应用程序 (.out)** - 应用程序 (.out)<br>**生成文件** - 生成文件<br>
STL 的使用 | 指定要用于此配置的 C++ 标准库。 | **共享 GNU 标准 C++ 库**<br>**静态 GNU 标准 C++ 库 (-static)**<br>
