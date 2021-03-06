---
title: "MFC 和 ATL 共享的类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 5e74a0fb32a9f0dc95837b9c8d633001ac79da8a
ms.contentlocale: zh-cn
ms.lasthandoff: 10/09/2017

---
# <a name="classes-shared-by-mfc-and-atl"></a>MFC 和 ATL 共享的类
下表列出了 MFC 和 atl。 之间共享的类  
  
|类|描述|头文件|  
|-----------|-----------------|-----------------|  
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|提供用于管理与文件相关联的日期和时间值的方法。|atltime.h|  
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|提供用于管理相对日期和时间值与文件相关联的方法。|atltime.h|  
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|表示具有固定的字符缓冲区的字符串对象。|cstringt.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|提供增强的位图支持，包括用于加载和采用 JPEG、 GIF、 BMP 和可移植网络图形 (PNG) 格式保存映像的功能。|atlimage.h|  
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|封装**日期**OLE 自动化中使用的数据类型。|atlcomtime.h|  
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|表示相对时间的时间范围。|atlcomtime.h|  
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|类似于 Windows 的类[点](../../mfc/reference/point-structure1.md)结构，它还包括成员函数以操作`CPoint`和**点**结构。|atltypes.h|  
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|类似于 Windows 的类[RECT](../../mfc/reference/rect-structure1.md)结构，它还包括成员函数以操作`CRect`对象和 Windows`RECT`结构。|atltypes.h|  
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|表示`CSimpleStringT`对象。|atlsimpstr.h|  
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|类类似于 Windows 大小的结构，这将实现相对坐标或位置。|atltypes.h|  
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|提供的自动资源清理`GetBuffer`和`ReleaseBuffer`调用上现有的`CStringT`对象。|atlsimpstr.h|  
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|表示字符串对象的数据。|atlsimpstr.h|  
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|表示`CStringT`对象。|cstringt.h （MFC 取决于） atlstr.h （MFC 独立于）|  
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|表示绝对时间和日期。|atltime.h|  
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|一段时间，它将内部存储为中的时间跨度的秒数。|atltime.h|  
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|表示的接口`CStringT`内存管理器。|atlsimpstr.h|  
  
## <a name="see-also"></a>另请参阅  
 [ATL/MFC 共享类](../../atl-mfc-shared/atl-mfc-shared-classes.md)



