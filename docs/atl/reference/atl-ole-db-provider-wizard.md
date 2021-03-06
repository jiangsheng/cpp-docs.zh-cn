---
title: "ATL OLE DB 提供程序向导 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.provider.overview
dev_langs: C++
helpviewer_keywords:
- ATL OLE DB Provider Wizard
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 170f10d06112969d9147c37b20572f0888140d0a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="atl-ole-db-provider-wizard"></a>ATL OLE DB 提供程序向导
此向导将创建构成的 OLE DB 提供程序的类。  
  
## <a name="remarks"></a>备注  
 从 Visual Studio 2008 开始，通过此向导生成的注册脚本将注册其 COM 组件**HKEY_CURRENT_USER**而不是**HKEY_LOCAL_MACHINE**。 若要修改此行为，请设置**为所有用户注册组件**ATL 向导的选项。  
  
 下表介绍 ATL OLE DB 提供程序向导的选项：  
  
 **短名称**  
 键入要创建的提供程序的短名称。 自动填充向导中的其他编辑框，将基于你在此处键入。 如果你想，你可以编辑其他名称框。  
  
 **组件类**  
 组件类的名称。 ProgID 的名称将更改以匹配此名称。  
  
 **特性化**  
 此选项指定向导是否将创建使用属性或模板声明提供程序类。 当选择此选项时，向导将使用而不是模板声明 （如果你创建特性化的项目，这是默认选项） 的属性。 清除此选项，向导将使用模板声明而不是属性 （如果你创建了非特性化项目，这是默认选项）。  
  
 如果你在创建非特性化项目时选择此选项，向导将警告你项目将被转换为特性化项目，并询问您是否继续与否。  
  
 **ProgID**  
 ProgID 或以编程方式标识符是你的应用程序可以使用而不是 GUID 的文本字符串。 ProgID 名称采用以下格式*Projectname.Coclassname*。  
  
 **Version**  
 你的提供程序的版本号。 默认值为 1。  
  
 **数据源类**  
 数据源类的名称，窗体 C*短名称*源。  
  
 **数据源.h 文件**  
 数据源类的标头文件。 你可以编辑此文件的名称，或选择一个现有的标头文件。  
  
 **会话类**  
 会话类中，C 在窗体的名称*短名称*会话。  
  
 **会话.h 文件**  
 会话类标头文件。 你可以编辑此文件的名称，或选择一个现有的标头文件。  
  
 **命令类**  
 命令类，C 在窗体的名称*短名称*命令。  
  
 **命令.h 文件**  
 命令类的标头文件。 此名称不能进行编辑，并且依赖于行集标头文件的名称。  
  
 **行集类**  
 行集类，C 在窗体的名称*短名称*行集。  
  
 **行集.h 文件**  
 行集类的标头文件。 你可以编辑此文件的名称，或选择一个现有的标头文件。  
  
 **行集.cpp 文件**  
 提供程序的实现文件。 你可以编辑此文件的名称，或选择一个现有的实现文件。  
  
## <a name="see-also"></a>另请参阅  
 [ATL OLE DB 访问接口](../../atl/reference/adding-an-atl-ole-db-provider.md)

