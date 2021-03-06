---
title: "从类型库向导添加类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.class.typelib
dev_langs: C++
helpviewer_keywords:
- Add Class from TypeLib Wizard [MFC]
- COM interfaces, adding classes
ms.assetid: 96152afd-9374-4649-a6ab-b0fa2a5592a3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0b4c56ccf67d5adae211925350dceaece3059cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="add-class-from-typelib-wizard"></a>从类型库添加类向导
使用此向导从可用的类型库添加 MFC 类。 该向导创建从所选的类型库添加每个接口的类。  
  
 **添加类**  
 指定从中创建类的类型库的位置。  
  
|选项|描述|  
|------------|-----------------|  
|**注册表**|在系统中注册的类型库。 已注册的类型库中列出**可用的类型库**。|  
|**文件**|类型库不一定在系统中注册，但包含在文件中。 必须提供文件的位置中**位置**。|  
  
 **可用的类型库**  
 列出系统中当前已注册的类型库。 选择此列表以显示在其接口从类型库**接口**列表。  
  
 请参阅"在分布式 COM:: 类型库和语言集成"有关注册类型库的详细信息的 MSDN 库中。  
  
 **位置**  
 指定的类型库的位置。 如果你单击**文件**下**从以下来源添加类**，你可以提供包含类型库的文件的位置。 若要浏览到文件的位置，单击省略号按钮。  
  
 **接口**  
 列出中当前选定的类型库中的接口**可用的类型库**列表。  
  
|传输按钮|描述|  
|---------------------|-----------------|  
|**>**|添加中当前选定的接口**接口**列表。 如果没有选定接口则灰显。|  
|**>>**|添加中当前选定的类型库中的所有接口**可用的类型库**列表。|  
|**<**|移除在当前选定的类**生成的类**列表。 如果没有任何类中当前选定灰显**生成的类**列表。|  
|**<\<**|删除中的所有类**生成的类**列表。 为灰色的如果**生成的类**列表为空。|  
  
 **生成的类**  
 指定要从使用添加的接口生成的类名称 **>** 或 **>>** 按钮。 你可以单击此框以选择类，然后使用向上或向下键滚动浏览列表中，查看在每个类名`Class`框和文件名称中的**文件**单击时，向导将生成的框**完成**。 你可以在此框中选择一次只有一个类。  
  
 你可以通过此列表中选择它并单击删除类 **<** 。 不需要在生成类中，若要删除所有类; 选择一个类通过单击 **<<** ，删除中的所有类**生成的类**框。  
  
 `Class`  
 指定在选定的类名称**生成的类**单击时，该向导将添加的框**完成**。 你可以编辑中的名称`Class`框。  
  
 **文件**  
 设置新的类的头文件的名称。 默认情况下，此名称基于你在中提供的名称**生成的类**。 单击省略号按钮，以将文件名称保存到你选择的位置，或者将类声明追加到现有文件。 如果你选择现有文件，向导将不将其保存到所选位置直到你单击**完成**向导中。  
  
 向导不会覆盖文件。 如果选择的名称的现有文件，则单击**完成**，向导会提示您指出类声明是否应追加到文件的内容。 单击**是**要追加文件; 单击**否**返回到向导并指定另一个文件的名称。  
  
## <a name="see-also"></a>另请参阅  
 [类型库中的 MFC 类](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)   
 [自动化客户端：使用类型库](../../mfc/automation-clients-using-type-libraries.md)

