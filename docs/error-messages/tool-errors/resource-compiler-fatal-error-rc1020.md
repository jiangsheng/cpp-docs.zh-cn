---
title: "资源编译器错误 RC1020 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1020"
ms.assetid: 3e073ebf-9136-4bf8-ac6a-3c642ed64594
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 资源编译器错误 RC1020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

意外的“\#endif”  
  
 出现 `#endif` 指令但没有匹配的 `#if`、**\#ifdef** 或 **\#ifndef** 指令。  
  
 确保每个 `#if`、**\#ifdef** 和 **\#ifndef** 语句都有匹配的 `#endif`。