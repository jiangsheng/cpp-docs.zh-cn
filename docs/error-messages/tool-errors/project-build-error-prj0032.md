---
title: "项目生成错误 PRJ0032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0032"
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 项目生成错误 PRJ0032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

项目级自定义生成步骤的“输出”属性包含“macro”（计算为“macro\_expansion”）。  
  
 项目的自定义生成步骤具有错误的输出，原因可能是宏计算问题。  该错误可能还意味着路径有格式错误，包含在文件路径中是非法的字符或字符组合。  
  
 若要解决该错误，请修复宏或修复路径说明。  计算出的路径是项目目录的绝对路径。