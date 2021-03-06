---
title: "调节按钮样式 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 92881b4c6bab1deaf35ba11e10dbea318194bd05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="spin-button-styles"></a>调节按钮样式
数值调节钮的设置的许多 ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) 由样式控制。 你可以设置使用的以下样式**属性**在对话框编辑器的窗口。  
  
-   **方向**垂直或水平。 控件的方向箭头按钮。 与关联`UDS_HORZ`样式。  
  
-   **对齐**之一未附加、 左侧或右侧。 控制数值调节钮的位置。 左侧和右侧位置数值调节钮合作者窗口的旁边。 减少合作者窗口的宽度以适应数值调节钮。 与关联`UDS_ALIGNLEFT`和`UDS_ALIGNRIGHT`样式。  
  
-   **自动合作者**自动为数值调节钮合作者窗口在 Z 顺序中选择上一个窗口。 在对话框模板中，这是之前数值调节钮的 tab 键顺序的控件。 与关联`UDS_AUTOBUDDY`样式。  
  
-   **设置 Buddy Integer**导致数值调节钮控件要递增或递减当前的位置更改作为合作者窗口的标题。 与关联`UDS_SETBUDDYINT`样式。  
  
-   **没有千位**不会插入千位分隔符的值在合作者窗口的标题中。 与关联`UDS_NOTHOUSANDS`样式。  
  
    > [!NOTE]
    >  如果你想要使用对话框数据交换 (DDX) 来从合作者控件中获取整数值，请设置此样式。 `DDX_Text`不接受嵌入千位分隔符。  
  
-   **包装**将导致"包装"由于值是递增或递减的控制范围以外的位置。 与关联`UDS_WRAP`样式。  
  
-   **箭头键**导致数值调节钮递增或递减位置按向上键和向下箭头键时。 与关联`UDS_ARROWKEYS`样式。  
  
## <a name="see-also"></a>另请参阅  
 [使用 CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [控件](../mfc/controls-mfc.md)

