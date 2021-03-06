---
title: "BLOB_ENTRY_LENGTH |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BLOB_ENTRY_LENGTH
dev_langs: C++
helpviewer_keywords: BLOB_ENTRY_LENGTH macro
ms.assetid: 832d21ab-5fdd-49ad-af6e-4fca5722ec93
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0de1707ab616aca49061590bfb76bf74360019ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="blobentrylength"></a>BLOB_ENTRY_LENGTH
与使用`BEGIN_COLUMN_MAP`和`END_COLUMN_MAP`要绑定的二进制大型对象 ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx))。 类似于[BLOB_ENTRY](../../data/oledb/blob-entry.md)，只不过此宏还获取以字节为单位的 BLOB 列的长度。  
  
## <a name="syntax"></a>语法  
  
```  
  
BLOB_ENTRY_LENGTH(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
,   
length  
 )  
  
```  
  
#### <a name="parameters"></a>参数  
 `nOrdinal`  
 [in] 列号。  
  
 *IID*  
 [in]接口的 GUID，如**IDD_ISequentialStream**，可用来检索 BLOB。  
  
 `flags`  
 [in]定义由 OLE 结构化存储模型的存储模式标志 (例如， **STGM_READ**)。  
  
 `data`  
 [in] 用户记录中的对应数据成员。  
  
 *length*  
 [out]BLOB 列 （实际） 长度以字节为单位。  
  
## <a name="example"></a>示例  
 请参阅[如何检索 BLOB？](../../data/oledb/retrieving-a-blob.md)。  
  
## <a name="requirements"></a>要求  
 **标头:** atldbcli.h  
  
## <a name="see-also"></a>另请参阅  
 [宏和全局函数 OLE DB 使用者模板](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)