---
title: "hash_set (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/hash_set> 标头 [STL/CLR]"
  - "<hash_set> 标头 [STL/CLR]"
  - "hash_set 类 [STL/CLR]"
ms.assetid: d110e356-ba3e-4e52-9e2d-d997bf975c96
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# hash_set (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

模板类描述一个控件对象访问双向元素的序列。更改长度  使用容器 `hash_set` 管理元素序列用作哈希表，每个表项目存储节点的双向链接列表要和每个节点存储的元素。  值每个元素对排序序列用作键。  
  
 在如下解释，`GValue` 与 `GKey`相同，然后与 `Key` 相同，除非是后者 ref 类型，在这种情况下，它是 `Key^`条件下。  
  
## 语法  
  
```  
template<typename Key>  
    ref class hash_set  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### 参数  
 键  
 受控序列中元素的键组件的类型。  
  
## 成员  
  
|类型定义|说明|  
|----------|--------|  
|[hash\_set::const\_iterator](../dotnet/hash-set-const-iterator-stl-clr.md)|受控序列的常量迭代器的类型。|  
|[hash\_set::const\_reference](../dotnet/hash-set-const-reference-stl-clr.md)|元素的常量引用的类型。|  
|[hash\_set::const\_reverse\_iterator](../dotnet/hash-set-const-reverse-iterator-stl-clr.md)|常数进行反向迭代器类型的控制的序列。|  
|[hash\_set::difference\_type](../dotnet/hash-set-difference-type-stl-clr.md)|\(可能\) 签名类型两个元素之间的距离。|  
|[hash\_set::generic\_container](../dotnet/hash-set-generic-container-stl-clr.md)|泛型接口的类型容器中。|  
|[hash\_set::generic\_iterator](../dotnet/hash-set-generic-iterator-stl-clr.md)|一迭代器的类型通用接口的容器的。|  
|[hash\_set::generic\_reverse\_iterator](../dotnet/hash-set-generic-reverse-iterator-stl-clr.md)|一进行反向迭代器的类型泛型接口的容器的。|  
|[hash\_set::generic\_value](../dotnet/hash-set-generic-value-stl-clr.md)|的元素类型泛型接口的容器的。|  
|[hash\_set::hasher](../dotnet/hash-set-hasher-stl-clr.md)|键的哈希委托。|  
|[hash\_set::iterator](../dotnet/hash-set-iterator-stl-clr.md)|受控序列的迭代器的类型。|  
|[hash\_set::key\_compare](../dotnet/hash-set-key-compare-stl-clr.md)|两个关键的委托。|  
|[hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md)|排序键的类型。|  
|[hash\_set::reference](../dotnet/hash-set-reference-stl-clr.md)|元素的引用的类型。|  
|[hash\_set::reverse\_iterator](../dotnet/hash-set-reverse-iterator-stl-clr.md)|一进行反向迭代器类型的控制的序列。|  
|[hash\_set::size\_type](../dotnet/hash-set-size-type-stl-clr.md)|非负数两个元素之间的距离 \(\) 类型。|  
|[hash\_set::value\_compare](../dotnet/hash-set-value-compare-stl-clr.md)|两个元素值排序的委托。|  
|[hash\_set::value\_type](../dotnet/hash-set-value-type-stl-clr.md)|元素的类型。|  
  
|成员函数|说明|  
|----------|--------|  
|[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)|指定受控序列的开头。|  
|[hash\_set::bucket\_count](../dotnet/hash-set-bucket-count-stl-clr.md)|计数存储桶的数目。|  
|[hash\_set::clear](../dotnet/hash-set-clear-stl-clr.md)|移除所有元素。|  
|[hash\_set::count](../dotnet/hash-set-count-stl-clr.md)|计数与指定键的元素。|  
|[hash\_set::empty](../dotnet/hash-set-empty-stl-clr.md)|测试元素不存在。|  
|[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)|指定受控序列的末尾。|  
|[hash\_set::equal\_range](../dotnet/hash-set-equal-range-stl-clr.md)|查找数组与指定键的。|  
|[hash\_set::erase](../dotnet/hash-set-erase-stl-clr.md)|移除指定位置处的元素。|  
|[hash\_set::find](../dotnet/hash-set-find-stl-clr.md)|查找与指定键匹配的元素。|  
|[hash\_set::hash\_delegate](../dotnet/hash-set-hash-delegate-stl-clr.md)|将键的哈希委托。|  
|[hash\_set::hash\_set](../dotnet/hash-set-hash-set-stl-clr.md)|构造容器对象。|  
|[hash\_set::insert](../dotnet/hash-set-insert-stl-clr.md)|添加元素。|  
|[hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)|复制两个键的委托。|  
|[hash\_set::load\_factor](../dotnet/hash-set-load-factor-stl-clr.md)|计数、元素每个存储桶。|  
|[hash\_set::lower\_bound](../dotnet/hash-set-lower-bound-stl-clr.md)|查找与指定的键范围的开头。|  
|[hash\_set::make\_value](../dotnet/hash-set-make-value-stl-clr.md)|构造值对象。|  
|[hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md)|获取或设置在最大元素每个存储桶。|  
|[hash\_set::rbegin](../dotnet/hash-set-rbegin-stl-clr.md)|指定反转的受控序列的开头。|  
|[hash\_set::rehash](../dotnet/hash-set-rehash-stl-clr.md)|重新生成哈希表。|  
|[hash\_set::rend](../dotnet/hash-set-rend-stl-clr.md)|指定反转的受控序列的末尾。|  
|[hash\_set::size](../dotnet/hash-set-size-stl-clr.md)|计算元素的数量。|  
|[hash\_set::swap](../dotnet/hash-set-swap-stl-clr.md)|交换两个容器的内容。|  
|[hash\_set::to\_array](../dotnet/hash-set-to-array-stl-clr.md)|复制控件序列到新数组。|  
|[hash\_set::upper\_bound](../dotnet/hash-set-upper-bound-stl-clr.md)|查找与指定的键范围的末尾。|  
|[hash\_set::value\_comp](../dotnet/hash-set-value-comp-stl-clr.md)|复制两个元素值排序的委托。|  
  
|运算符|说明|  
|---------|--------|  
|[hash\_set::operator\=](../dotnet/hash-set-operator-assign-stl-clr.md)|控件替换序列。|  
  
## 接口  
  
|接口|说明|  
|--------|--------|  
|<xref:System.ICloneable>|复制对象。|  
|<xref:System.Collections.IEnumerable>|通过序列元素。|  
|<xref:System.Collections.ICollection>|维护元素组。|  
|<xref:System.Collections.Generic.IEnumerable%601>|序列通过输出元素。|  
|<xref:System.Collections.Generic.ICollection%601>|打印维护元素组。|  
|IHashKey\<值，\>|维护型容器。|  
  
## 备注  
 对象将它控制序列中未使用助记域，当一双向链接列表的各个节点。  若要加快访问，对象还维护着指针到列表 \(哈希表\)，有效管理整个列表为子表序列或存储桶的更改长度数组。  它从不将元素插入到它保持顺序通过修改节点之间的链接存储桶，通过复制一节点内容到另一个。  这表示您可以自由插入和移除元素，而不干扰的其余元素。  
  
 它通过调用类型 [hash\_set::key\_compare](../dotnet/hash-set-key-compare-stl-clr.md)一个存储委托对象控制的对象对每个存储桶。  在构造 hash\_set 时，则可以存储指定的委托对象；如果您不指定委托对象，默认是比较 `operator<=(key_type, key_type)`。  
  
 通过调用成员函数访问存储的委托对象`()`。[hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md) 此委托对象必须定义排序等效类型之间 [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md)键。  这意味着，任何两键的 `X` 和 `Y`:  
  
 `key_comp()(X, Y)` 返回对每调用相同的布尔值结果。  
  
 如果 `key_comp()(X, Y) && key_comp()(Y, X)` 为 true，则 `X` 和 `Y` 是具有相同订单。  
  
 的行为与 `operator<=(key_type, key_type)`、`operator>=(key_type, key_type)` 或 `operator==(key_type, key_type)` 中的所有顺序的规则定义 eqivalent 顺序。  
  
 注意确保密钥容器只具有相同订单的元素 \(和散列为相同值，整数\) 在存储桶中是连续的。  与不同类模板 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)，模板类 `hash_set` 对象确保所有元素的键是唯一的。\(两键没有等效顺序。\)  
  
 对象确定哪个存储桶。应该通过调用类型 [hash\_set::hasher](../dotnet/hash-set-hasher-stl-clr.md)一个存储委托对象包含特定订单的键。  通过调用成员函数 [hash\_set::hash\_delegate](../dotnet/hash-set-hash-delegate-stl-clr.md)`()` 获取依赖于键值的整数值访问该存储区的对象。  在构造 hash\_set 时，则可以存储指定的委托对象；如果您不指定委托对象，默认是函数 `System::Object::hash_value(key_type)`。  这意味着，任何键的 `X` 和 `Y`:  
  
 `hash_delegate()(X)` 返回对每次调用的相同结果整数。  
  
 如果 `X` 和 `Y` 具有相同订单，则 `hash_delegate()(X)` 应返回整数结果与 `hash_delegate()(Y)`相同。  
  
 每个元素用作键和值。  序列以使查找、任意元素插入和删除。许多操作的是元素数独立于序列的方法 \(时间\) 的常量\-\-至少在情况最好。  而且，插入元素无效迭代器，并且，移除元素无效点在所移除的元素的那些迭代器。  
  
 如果哈希值不是统一分发，但是，哈希表可以降低。  非常\-\-对于始终返回相同值的哈希函数\-\-查找、插入和删除的元素数成比例在序列 \(线性时间\)。  容器竭力选择合理的哈希函数、平均存储桶大小和 Hashtable 大小 \(存储桶的总数\)，但是，您可以重写其中一个或所有这些选择。  例如，参见，函数和 [hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md)[hash\_set::rehash](../dotnet/hash-set-rehash-stl-clr.md)。  
  
 hash\_set 支持双向迭代器，这意味着可以单步执行到相邻元素使迭代器指定控制在序列中的元素。  特定头节点对应于 [hash\_set::end](../dotnet/hash-set-end-stl-clr.md)返回`()`的迭代器。  如果有可以减小此迭代器达到控制序列中的最后一个元素。  可以增加 hash\_set 迭代器达到头节点，并且，则将比较与 `end()`。  但是，您无法取消引用 `end()`返回的迭代器。  
  
 注意不可以引用 hash\_set 元素直接为其数字的位置\-\-这要求一个随机访问迭代器。  
  
 hash\_set 迭代器存储句柄与其关联 hash\_set 节点，而后者存储句柄及其关联的容器。  可以只使用迭代器与它们关联的容器对象。  只要其关联 hash\_set 节点与某些 hash\_set，hash\_set 迭代器仍然有效。  而且，有效的迭代器 dereferencable\-\-可以使用该指定的或修改值访问该元素\-\-只要它不等于 `end()`。  
  
 清除或移除元素调用其存储值的析构函数。  销毁容器清除所有元素。  因此，元素类型为 ref 类的容器元素确保不活动。的容器时间。  注释，但是，容器处理执行销毁 `not` 元素。  
  
## 要求  
 **页眉：** \<cliext\/hash\_set\>  
  
 **命名空间：** cliext  
  
## 请参阅  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [集合](../dotnet/set-stl-clr.md)   
 [集合](../dotnet/set-stl-clr.md)   
 [集合](../dotnet/set-stl-clr.md)   
 [STL\/CLR 库](../dotnet/stl-clr-library-reference.md)