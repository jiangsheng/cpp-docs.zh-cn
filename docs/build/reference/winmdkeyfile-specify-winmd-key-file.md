---
title: "/WINMDKEYFILE（指定 winmd 密钥文件） | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.WINMDKeyFile"
dev_langs: 
  - "C++"
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /WINMDKEYFILE（指定 winmd 密钥文件）
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定一个密钥或密钥对以登录 Windows 运行时元数据\(.winmd\) 文件。  
  
```  
  
/WINMDKEYFILE:filename  
  
```  
  
## 备注  
 类似于应用到 .winmd 文件的 [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) 链接器选项。  
  
### 在 Visual Studio 开发环境中设置此链接器选项  
  
1.  打开项目的**“属性页”**对话框。  有关详细信息，请参见[使用项目属性](../../ide/working-with-project-properties.md)。  
  
2.  选择 **Linker** 文件夹。  
  
3.  选择**“Windows 元数据”**属性页。  
  
4.  在**Windows 元数据关键文件** 框中，输入 文件位置。  
  
## 请参阅  
 [设置链接器选项](../../build/reference/setting-linker-options.md)   
 [链接器选项](../../build/reference/linker-options.md)