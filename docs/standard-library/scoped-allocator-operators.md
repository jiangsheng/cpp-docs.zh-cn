---
title: "&lt;scoped_allocator&gt; 运算符 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
dev_langs: C++
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
caps.latest.revision: "10"
manager: ghogen
ms.openlocfilehash: d29a5a99f261776468364717a13b90a1ddde5216
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="ltscopedallocatorgt-operators"></a>&lt;scoped_allocator&gt; 运算符
|||  
|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>operator!=  
 测试两个 `scoped_allocator_adaptor` 对象是否不相等。  
  
```cpp  
template <class Outer, class... Inner>  
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,  
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;  
```  
  
### <a name="parameters"></a>参数  
 `left`  
 左 `scoped_allocator_adaptor` 对象。  
  
 `right`  
 正确的 `scoped_allocator_adaptor` 对象。  
  
### <a name="return-value"></a>返回值  
 `!(left == right)`  
  
##  <a name="op_eq_eq"></a>operator==  
 测试两个 `scoped_allocator_adaptor` 对象是否相等。  
  
```cpp  
template <class Outer, class... Inner>  
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,  
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;  
```  
  
### <a name="parameters"></a>参数  
 `left`  
 左 `scoped_allocator_adaptor` 对象。  
  
 `right`  
 正确的 `scoped_allocator_adaptor` 对象。  
  
### <a name="return-value"></a>返回值  
 `left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`  
  
## <a name="see-also"></a>另请参阅  
 [<scoped_allocator>](../standard-library/scoped-allocator.md)

