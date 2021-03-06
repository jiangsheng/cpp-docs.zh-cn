---
title: "下标运算符的解释 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- subscript operator [C++], interpretation of
- arrays [C++], subscripting
- interpreting subscript operators [C++]
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1a83ff6aea4380688d3b6298b93e04caab1dbb7f
ms.contentlocale: zh-cn
ms.lasthandoff: 09/25/2017

---
# <a name="interpretation-of-subscript-operator"></a>下标运算符的解释
与其他运算符，下标运算符相似 (**[]**) 可以由用户重新定义。 如果没有重载下标运算符，下标运算符的默认行为是使用以下方法组合数组名称和下标：  
  
 \*((*数组名称*) + (*下标*))  
  
 像涉及指针类型的所有加法中一样，缩放将自动执行以调整类型的大小。 因此，所得到的值不是*下标*字节的原点*数组名称*; 相反，它是*下标*th 元素的数组。 (有关此转换的详细信息，请参阅[相加运算符](../cpp/additive-operators-plus-and.md)。)  
  
 同样，对于多维数组，将使用以下方法获取地址：  
  
 **((**   
 ***阵列名称*) + （**   
 ***下标*1***max*2 * \* max*3*....max 表示*n) ** + ***下标*2 * \* max*3*....max 表示*n)。   。 。 *+**下标*n))  
  
## <a name="see-also"></a>另请参阅  
 [阵列](../cpp/arrays-cpp.md)
