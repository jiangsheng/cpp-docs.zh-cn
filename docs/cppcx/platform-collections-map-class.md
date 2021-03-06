---
title: "Platform::Collections::Map 类 |Microsoft 文档"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Collections::Map::Map
- COLLECTION/Platform::Collections::Map::Clear
- COLLECTION/Platform::Collections::Map::First
- COLLECTION/Platform::Collections::Map::GetView
- COLLECTION/Platform::Collections::Map::HasKey
- COLLECTION/Platform::Collections::Map::Insert
- COLLECTION/Platform::Collections::Map::Lookup
- COLLECTION/Platform::Collections::Map::Remove
- COLLECTION/Platform::Collections::Map::Size
dev_langs: C++
helpviewer_keywords: Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 3cf7cec405170a1bb1ee02cfd076c78c43524c74
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections::Map 类
表示一个 *映射*，它是键值对的集合。  
  
## <a name="syntax"></a>语法  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = std::less<K>>  
ref class Map sealed;  
```  
#### <a name="parameters"></a>参数  
 `K`  
 键值对中键的类型。  
  
 `V`  
 键值对中值的类型。  
  
 `C`  
 提供一个函数对象的类型，该对象可以将两个元素值作为排序键加以比较，以决定它们在映射中的相对顺序。 默认情况下， [std:: less\<K >](../standard-library/less-struct.md)。  
  
 __is_valid_winrt_type()  
 编译器生成的函数，用于验证 K 和 V 类型，并在此类型无法存储在映射中时提供友好错误消息。  
  
### <a name="remarks"></a>备注  
 允许的类型包括：  
  
-   整数  
  
-   接口类 ^  
  
-   公共 ref 类  
  
-   value struct  
  
-   公共枚举类  
  
 映射基本上是 [std::map](../standard-library/map-class.md)的包装器。 它是 c + + 具体实现[Windows::Foundation::Collections::IMap < Windows::Foundation::Collections::IKeyValuePair\<K，V >>](http://go.microsoft.com/fwlink/p/?LinkId=262408)和[IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx)Windows 运行时接口的公共之间传递的类型。 如果你尝试在公共返回值或参数中使用 `Platform::Collections::Map` 类型，则将引发编译器错误 C3986。 可通过更改参数或返回值的类型来修复该错误[Windows::Foundation::Collections::IMap\<K，V >](http://go.microsoft.com/fwlink/p/?LinkId=262408)。  
  
 有关详细信息，请参阅[集合](../cppcx/collections-c-cx.md)。  
  
### <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[Map:: map](#ctor)|初始化 Map 类的新实例。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[Map:: clear](#clear)|从当前 Map 对象中移除所有键值对。|  
|[Map:: first](#first)|返回指定映射中第一个元素的迭代器。|  
|[Map:: getview](#getview)|返回当前映射的只读视图，即 [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)。|  
|[Map:: haskey](#haskey)|确定当前 Map 中是否包含指定键。|  
|[Map:: insert](#insert)|将指定的键值对添加到当前 Map 对象中。|  
|[Map:: lookup](#lookup)|检索当前 Map 对象中指定键处的元素。|  
|[Map:: remove](#remove)|从当前 Map 对象中删除指定的键值对。|  
|[Map:: size](#size)|返回当前 Map 对象中的元素数目。|  
  
### <a name="events"></a>事件  
  
|||  
|-|-|  
|名称|描述|  
|[Map:: mapchanged](#mapchanged-event.md)`event`|当映射更改时发生。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `Map`  
  
### <a name="requirements"></a>要求  
 **标头：** collection.h  
  
 **命名空间：** Platform::Collections  

## <a name="clear"></a>Map:: clear 方法
从当前 Map 对象中移除所有键值对。  
  
### <a name="syntax"></a>语法  
  
```    
virtual void Clear();   
```  
  


## <a name="first"></a>Map:: first 方法
返回指定映射中第一个元素的迭代器，如果映射为空，则返回 `nullptr`。  
  
### <a name="syntax"></a>语法  
  
```    
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
### <a name="return-value"></a>返回值  
 指定映射中第一个元素的迭代器。  
  
### <a name="remarks"></a>备注  
 保留 first 返回的迭代器一种简便方式是将返回值分配给使用声明的变量**自动**类型推导关键字。 例如 `auto x = myMap->First();`。  
  


## <a name="getview"></a>Map:: getview 方法
返回当前 Map 中; 的只读视图也就是说， [Platform::Collections::MapView 类](../cppcx/platform-collections-mapview-class.md)，该类实现[Windows::Foundation::Collections::IMapView\<K，V >](http://msdn.microsoft.com/library/windows/apps/br226037.aspx)接口。  
  
### <a name="syntax"></a>语法  
  
```    
Windows::Foundation::Collections::IMapView<K, V>^ GetView();  
```  
  
### <a name="return-value"></a>返回值  
 一个 `MapView` 对象。  
  


## <a name="haskey"></a>Map:: haskey 方法
确定当前 Map 中是否包含指定键。  
  
### <a name="syntax"></a>语法  
  
```    
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>参数  
 `key`  
 用于定位 Map 元素的键。 一种`key`名称*K*。  
  
### <a name="return-value"></a>返回值  
 如果找到该键，则为 `true`；否则为 `false`。  
  


## <a name="insert"></a>Map:: insert 方法
将指定的键值对添加到当前 Map 对象中。  
  
### <a name="syntax"></a>语法  
  
```  
  
virtual bool Insert(K key, V value);  
```  
  
### <a name="parameters"></a>参数  
 `key`  
 键值对中的键部分。 一种`key`名称*K*。  
  
 `value`  
 键值对中的值部分。 一种`value`名称*V*。  
  
### <a name="return-value"></a>返回值  
 如果当前映射中一个现有元素的键匹配 `true` 并且该元素的值部分设置为 `key`，则为 `value`。 如果当前映射中没有任何现有元素匹配 `false` 并且 `key` 和 `key` 参数构成键值对并随后添加到当前映射中，则为 `value`。  
  


## <a name="lookup"></a>Map:: lookup 方法
检索与类型 K 的指定键关联的类型 V 的值（如果键存在）。  
  
### <a name="syntax"></a>语法  
  
```  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>参数  
 `key`  
 用于定位映射中的元素的键。 一种`key`名称*K*。  
  
### <a name="return-value"></a>返回值  
 与 `key` 配对的值。 返回值的类型是 e *V*。  
  
### <a name="remarks"></a>备注  
 如果不存在该键，则[platform:: outofboundsexception](../cppcx/platform-outofboundsexception-class.md)引发。  
  


## <a name="ctor"></a>Map:: map 构造函数
初始化 Map 类的新实例。  
  
### <a name="syntax"></a>语法  
  
```  
explicit Map(const C& comp = C());  
explicit Map(const StdMap& m);  
explicit Map(StdMap&& m ;  
template <typename InIt>  
Map(  
   InItfirst,  
   InItlast,  
   const C& comp = C());  
```  
  
### <a name="parameters"></a>参数  
 `InIt`  
 当前映射的类型名称。  
  
 `comp`  
 提供一个函数对象的类型，该对象可以将两个元素值作为排序键加以比较，以决定它们在映射中的相对顺序。  
  
 `m`  
 引用或[Lvalues 和 Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)到`map Class`用于初始化当前映射。  
  
 `first`  
 用于初始化当前映射的一系列元素中的第一个元素的输入迭代器。  
  
 `last`  
 用于初始化当前映射的一系列元素之后的第一个元素的输入迭代器。  
  


## <a name="mapchanged"></a>Map:: mapchanged 事件
项目插入到映射中或从映射中移除时引发。  
  
### <a name="syntax"></a>语法  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
### <a name="property-valuereturn-value"></a>属性值/返回值  
 A [MapChangedEventHandler\<K，V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) ，包含有关引发该事件，然后所发生的更改类型的对象信息。 另请参阅[IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx)和[CollectionChange 枚举](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx)。  
  
## <a name="net-framework-equivalent"></a>.NET Framework 等效项  
 使用 C# 或 Visual Basic 的 Windows 应用商店应用项目 IMap\<K，V > 作为 IDictionary\<K，V >。  
  


## <a name="remove"></a>Map:: remove 方法
从当前 Map 对象中删除指定的键值对。  
  
### <a name="syntax"></a>语法  
  
```    
virtual void Remove(K key);  
```  
  
### <a name="parameters"></a>参数  
 `key`  
 键值对中的键部分。 一种`key`名称*K*。  
  


## <a name="size"></a>Map:: size 方法
返回的数目[Windows::Foundation::Collections::IKeyValuePair\<K，V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)映射中的元素。  
  
### <a name="syntax"></a>语法  
  
```    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>返回值  
 Map 中的元素数目。  
  

  
## <a name="see-also"></a>另请参阅  
 [平台 Namespace](platform-namespace-c-cx.md)   
 [C + + 创建 Windows 运行时组件](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)