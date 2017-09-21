---
title: "滚动条样式 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SBS_VERT
- SBS_SIZEBOXBOTTOMRIGHTALIGN
- SBS_LEFTALIGN
- SBS_RIGHTALIGN
- SBS_TOPALIGN
- SBS_SIZEBOXTOPLEFTALIGN
- SBS_BOTTOMALIGN
- SBS_SIZEBOX
- SBS_HORZ
dev_langs:
- C++
helpviewer_keywords:
- SBS_HORZ constant
- SBS_TOPALIGN constant
- SBS_SIZEBOX constant
- SBS_BOTTOMALIGN constant
- SBS_VERT constant
- SBS_LEFTALIGN constant
- SBS_SIZEBOXBOTTOMRIGHTALIGN constant
- scroll bars, styles
- SBS_SIZEBOXTOPLEFTALIGN constant
- SBS_RIGHTALIGN constant
ms.assetid: 8bcde35b-387d-49ae-bdd6-7cda9f5dae26
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 778fe7b0f6f6319884df4ed9c5ccbe8e34bd8d42
ms.contentlocale: zh-cn
ms.lasthandoff: 02/24/2017

---
# <a name="scroll-bar-styles"></a>滚动条样式
-   **SBS_BOTTOMALIGN**用于**SBS_HORZ**样式。 滚动条的下边缘对齐在所指定的矩形的下边缘**创建**成员函数。 滚动条都有系统滚动条的默认高度。  
  
-   **SBS_HORZ**指定水平滚动条。 如果既没有**SBS_BOTTOMALIGN** ，也不**SBS_TOPALIGN**指定样式、 滚动条具有高度、 宽度和位置中给出**创建**成员函数。  
  
-   **SBS_LEFTALIGN**用于**SBS_VERT**样式。 滚动条的左边的缘对齐在所指定的矩形的左边缘**创建**成员函数。 滚动条具有系统滚动条的默认宽度。  
  
-   **SBS_RIGHTALIGN**用于**SBS_VERT**样式。 滚动条的右边缘对齐在所指定的矩形的右边缘与**创建**成员函数。 滚动条具有系统滚动条的默认宽度。  
  
-   **SBS_SIZEBOX**指定大小框。 如果既没有**SBS_SIZEBOXBOTTOMRIGHTALIGN** ，也不**SBS_SIZEBOXTOPLEFTALIGN**指定样式、 大小框具有高度、 宽度和位置中给出**创建**成员函数。  
  
-   **SBS_SIZEBOXBOTTOMRIGHTALIGN**用于**SBS_SIZEBOX**样式。 与在指定的矩形的右下角对齐大小中的右下角**创建**成员函数。 大小中有系统大小框的默认大小。  
  
-   **SBS_SIZEBOXTOPLEFTALIGN**用于**SBS_SIZEBOX**样式。 与在指定的矩形的左上角对齐大小中的左上角**创建**成员函数。 大小中有系统大小框的默认大小。  
  
-   **SBS_SIZEGRIP**相同**SBS_SIZEBOX**，但带凸起边缘。  
  
-   **SBS_TOPALIGN**用于**SBS_HORZ**样式。 滚动条的上边缘对齐在所指定的矩形的上边缘**创建**成员函数。 滚动条都有系统滚动条的默认高度。  
  
-   **SBS_VERT**指定垂直滚动条。 如果既没有**SBS_RIGHTALIGN** ，也不**SBS_LEFTALIGN**指定样式、 滚动条具有高度、 宽度和位置中给出**创建**成员函数。  
  
## <a name="see-also"></a>另请参阅  
 [MFC 使用的样式](../../mfc/reference/styles-used-by-mfc.md)   
 [CScrollBar::Create](../../mfc/reference/cscrollbar-class.md#create)   
 [滚动条控件样式](http://msdn.microsoft.com/library/windows/desktop/bb787533)

