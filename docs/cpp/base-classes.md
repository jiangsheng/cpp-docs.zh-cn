---
title: "基类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 200dc2a4bb53365c15457f016ac391bb48d4c278
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="base-classes"></a>基本类
继承过程将创建一个新的派生类，它由基类的成员加上派生类添加的任何新成员组成。 在多重继承中，可以构建一个继承关系图，其中相同的基类是多个派生类的一部分。 下图显示了此类关系图。  
  
 ![基类的多个实例](../cpp/media/vc38xn1.gif "vc38XN1")  
单个基类的多个实例  
  
 在该图中，显示了 `CollectibleString` 和 `CollectibleSortable` 的组件的图形化表示形式。 但是，基类 `Collectible` 位于通过 `CollectibleSortableString` 路径和 `CollectibleString` 路径的 `CollectibleSortable` 中。 若要消除此冗余，可以在继承此类类时将其声明为虚拟基类。  
  
