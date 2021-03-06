---
title: "使用手动访问器 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3a37f721c372f3ad11000aec023ef74fb1fb1097
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="using-manual-accessors"></a>使用手动访问器
有四个事项需要时处理未知的命令执行的操作：  
  
-   确定参数  
  
-   执行命令  
  
-   确定输出列  
  
-   查看是否存在多个返回行集  
  
 若要使用 OLE DB 使用者模板执行此操作，使用`CManualAccessor`类并按照以下步骤：  
  
1.  打开`CCommand`对象`CManualAccessor`作为模板参数。  
  
    ```  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  查询的会话**IDBSchemaRowset**接口，并使用过程参数行集。 如果**IDBSchemaRowset**接口不可用，查询`ICommandWithParameters`接口。 调用`GetParameterInfo`有关信息。 如果两个接口都可用，你可以假定没有参数。  
  
3.  对于每个参数，调用`AddParameterEntry`必须添加参数并设置它们。  
  
4.  打开行集，但将绑定参数设置为**false**。  
  
5.  调用`GetColumnInfo`检索输出列。 使用`AddBindEntry`向绑定添加输出列。  
  
6.  调用`GetNextResult`以确定多个行集是否可用。 重复步骤 2 至 5。  
  
 手动访问器的示例，请参阅**CDBListView::CallProcedure**中[DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)示例。  
  
## <a name="see-also"></a>另请参阅  
 [使用访问器](../../data/oledb/using-accessors.md)