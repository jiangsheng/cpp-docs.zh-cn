---
title: "&lt;hash_set&gt; 函数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: 4fcd6f0d72d31823a0d35108f087f2ad680e2f48
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; 函数
|||  
|-|-|  
|[swap](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|  
  
##  <a name="swap"></a>swap  
  
> [!NOTE]
>  此 API 已废弃不用。 替代项为 [unordered_set 类](../standard-library/unordered-set-class.md)。  
  
 交换两个 hash_set 的元素。  
  
```
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>参数  
 `right`  
 提供要交换的元素的 hash_set 或其元素要与 hash_set `left` 的元素进行交换的 hash_set。  
  
 `left`  
 其元素将与 hash_set `right` 的元素进行交换的 hash_set。  
  
### <a name="remarks"></a>备注  
 `swap` 模板函数是容器类 hash_set 上专用化的算法，用以执行成员函数 `left.`[swap](../standard-library/hash-set-class.md#swap)( `right`)。 这是由编译器进行的函数模板偏序实例。 模板函数以此种方式重载时，模板与函数调用的匹配并不唯一，随后编译器会选择此模板函数的最专用化版本。 模板函数的通用版本   
  
 **template \<class T> void swap(T&, T&),**   
  
 在此算法中，类按赋值进行工作，这是一种慢速操作。 每个容器中的专用化版本速度快很多，因为专用化版本可适用于容器类的内部表示形式。  
  
   
  
### <a name="example"></a>示例  
  有关使用 `swap` 的模板版本的示例，请参阅成员类 [hash_set::swap](../standard-library/hash-set-class.md#swap) 的代码示例。  
  
##  <a name="swap_hash_multiset"></a>swap (hash_multiset)  
  
> [!NOTE]
>  此 API 已废弃不用。 替代项为 [unordered_set 类](../standard-library/unordered-set-class.md)。  
  
 交换两个 hash_multiset 的元素。  
  
```
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>参数  
 `right`  
 提供要交换的元素的 hash_multiset 或其元素要与 hash_multiset `left` 的元素进行交换的 hash_multiset。  
  
 `left`  
 其元素将与 hash_multiset `right` 的元素进行交换的 hash_multiset。  
  
### <a name="remarks"></a>备注  
 `swap` 模板函数是容器类 hash_multiset 上专用化的算法，用以执行成员函数 `left.`[swap](../standard-library/hash-multiset-class.md#swap)( `right`)。 这是由编译器进行的函数模板偏序实例。 模板函数以此种方式重载时，模板与函数调用的匹配并不唯一，随后编译器会选择此模板函数的最专用化版本。 模板函数的通用版本   
  
 **template \<class T> void swap(T&, T&),**   
  
 在此算法中，类按赋值进行工作，这是一种慢速操作。 每个容器中的专用化版本速度快很多，因为专用化版本可适用于容器类的内部表示形式。  
  
   
  
### <a name="example"></a>示例  
  有关使用 `swap` 的模板版本的示例，请参阅成员类 [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) 的代码示例。  
  
## <a name="see-also"></a>另请参阅  
 [<hash_set>](../standard-library/hash-set.md)



