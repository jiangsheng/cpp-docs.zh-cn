---
title: "编译器警告 （等级 1） C4445 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4445
dev_langs: C++
helpviewer_keywords: C4445
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c31e9fa08b5aad05fef8af64f29eb75bc136e0f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4445"></a>编译器警告（等级 1）C4445
“function”: 在 WinRT 或托管类型中，虚方法不能为私有方法  
  
 如果虚函数是私有函数，则它无法由派生类型访问。 若要修复此错误，请将虚拟成员函数的可访问性更改为受保护或公共。