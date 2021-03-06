---
title: "ConvertBSTRToString |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ConvertBSTRToString
dev_langs:
- C++
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c559509083d21ff8b742ef80a55ac161bbca2f53
ms.contentlocale: zh-cn
ms.lasthandoff: 09/25/2017

---
# <a name="convertbstrtostring"></a>ConvertBSTRToString
**Microsoft 专用**  
  
 将转换`BSTR`值赋给**char \* **。  
  
## <a name="syntax"></a>语法  
  
```  
  
      char* __stdcall ConvertBSTRToString(  
   BSTR pSrc  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pSrc`  
 BSTR 变量。  
  
## <a name="remarks"></a>备注  
 `ConvertBSTRToString` 分配必须删除的字符串。  
  
## <a name="example"></a>示例  
  
```  
// ConvertBSTRToString.cpp  
#include <comutil.h>  
#include <stdio.h>  
  
#pragma comment(lib, "comsuppw.lib")  
  
int main() {  
   BSTR bstrText = ::SysAllocString(L"Test");  
   wprintf_s(L"BSTR text: %s\n", bstrText);  
  
   char* lpszText2 = _com_util::ConvertBSTRToString(bstrText);  
   printf_s("char * text: %s\n", lpszText2);  
  
   SysFreeString(bstrText);  
   delete[] lpszText2;  
}  
```  
  
```Output  
BSTR text: Test  
char * text: Test  
```  
  
**结束 Microsoft 专用**  
  
## <a name="requirements"></a>要求  
 **标头：** comutil.h。  
  
 **Lib:**对 comsuppw.lib 或 comsuppwd.lib (请参阅[/zc: wchar_t （wchar_t 是本机类型）](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)有关详细信息)  
  
## <a name="see-also"></a>另请参阅  
 [编译器 COM 全局函数](../cpp/compiler-com-global-functions.md)
