---
title: "分配零内存 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9708f8939ff32f9320e7c8e803753e801ce9448f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="allocating-zero-memory"></a>分配零内存
**ANSI 4.10.3** 请求的大小为零时，`calloc`、`malloc` 或 `realloc` 函数的行为  
  
 `calloc`、`malloc` 和 `realloc` 函数接受零作为参数。 不分配实际内存，但会返回有效的指针，并且之后可通过 realloc 修改内存块。  
  
## <a name="see-also"></a>另请参阅  
 [库函数](../c-language/library-functions.md)