---
title: "添加 ATL 消息处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a30c8d2c26893ddf101d7084a91215c7ed55bf48
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="adding-an-atl-message-handler"></a>添加 ATL 消息处理程序
若要添加到控件的消息处理程序 （处理 Windows 消息的成员函数），首先在类视图中选择的控件。 然后打开**属性**窗口中，选择**消息**图标，然后单击下拉列表中相反的必需的消息框控件。 这将在控件的标头文件和控件的.cpp 文件中的处理程序的主干实现中添加消息处理程序的声明。 它还将添加的消息映射，并为该处理程序添加一个条目。  
  
 ATL 中添加消息处理程序是类似于向 MFC 类中添加消息处理程序。 请参阅[添加 MFC 消息处理程序](../mfc/reference/adding-an-mfc-message-handler.md)有关详细信息。  
  
 以下条件仅适用于添加 ATL 消息处理程序：  
  
-   消息处理程序遵循与 MFC 的同一命名约定。  
  
-   新的消息映射项被添加到的主消息映射。 向导无法识别备用消息映射和链接。  
  
## <a name="see-also"></a>另请参阅  
 [实现窗口](../atl/implementing-a-window.md)

