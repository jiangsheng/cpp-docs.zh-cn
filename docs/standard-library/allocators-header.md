---
title: "&lt;allocators&gt; | Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <allocators>
dev_langs:
- C++
helpviewer_keywords:
- allocators header
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: cf6f722eaa4f71a808ec416aa7646c7fe4de2689
ms.contentlocale: zh-cn
ms.lasthandoff: 10/03/2017

---
# <a name="ltallocatorsgt"></a>&lt;allocators&gt;
定义多个模板，帮助为基于节点的容器分配和释放内存块。  
  
## <a name="syntax"></a>语法  
  
```  
#include <allocators>  
```  
  
## <a name="remarks"></a>备注  
 \< allocators> 标头提供六种分配器模板，可用于为基于节点的容器选择内存管理策略。 对于使用这些模板，它还提供多种不同的同步筛选器，以将内存管理策略定制到各种不同的多线程方案（包括无）。 为已知内存使用模式匹配内存管理策略以及为特定应用程序同步请求通常可以提升速度，或减少应用程序的总体内存要求。  
  
 分配器模板使用重用的组件来实现，可以进行自定义或被替换，以提供额外的内存管理策略。  
  
 C++ 标准库中基于节点的容器（std::list、std::set、std::multiset、std::map 和 std::multimap）将其元素存储在单独节点中。 针对特定容器类型的所有节点都具有相同大小，因此无需内存管理器常规用途的灵活性。 因为已在编译时知道每个内存块的大小，所以内存管理器可以更简单、更快。  
  
 在并非基于节点的容器中使用时（如 C++ 标准库容器 std::vector std::deque 和 std::basic_string），分配器模板将正确工作，但可能不会对默认分配器提供任何性能改进。  
  
 分配器模板类描述一个对象，用于管理所指定类型的对象数组的存储分配和释放。 分配器对象由 C++ 标准库中的多个分配器模板类所使用。  
  
 分配器是此类型的所有模板：  
  
 `template<class` `Type` `>`  
  
 `class allocator;`  
  
 其中模板参数 `Type` 是由分配器实例所管理的类型。 C++ 标准库提供默认分配器和在 [\<memory>](../standard-library/memory.md) 中定义的模板类 [allocator](../standard-library/allocator-class.md)。 \<allocators> 标头提供以下分配器：  
  
- [allocator_newdel](../standard-library/allocator-newdel-class.md)  
  
- [allocator_unbounded](../standard-library/allocator-unbounded-class.md)  
  
- [allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)  
  
- [allocator_variable_size](../standard-library/allocator-variable-size-class.md)  
  
- [allocator_suballoc](../standard-library/allocator-suballoc-class.md)  
  
- [allocator_chunklist](../standard-library/allocator-chunklist-class.md)  
  
 在创建容器时，将相应的分配器实例化用作第二个类型参数，如以下代码示例。  
  
 `#include <list>`  
  
 `#include <allocators>`  
  
 `std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;`  
  
 _List0 使用 `allocator_chunklist` 和默认的同步筛选器来分配节点。  
  
 使用宏 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 来创建具有同步筛选器的分配器模板而非默认模板。  
  
 `#include <list>`  
  
 `#include <allocators>`  
  
 `ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);`  
  
 `std::list<int, alloc<int> > _List1;`  
  
 _Lst1 使用 `allocator_chunklist` 和 [sync_per_thread](../standard-library/sync-per-thread-class.md) 同步筛选器来分配节点。  
  
 块分配器是一个缓存或筛选器。 缓存是采用一种参数类型为 std::size_t 的模板类。 它定义分配和释放单个大小内存块的块分配器。 它必须使用 `new` 运算符获取内存，但无需为每个块单独调用运算符 `new`。 例如，从较大块或缓存释放分配块进行子分配，以用于后续的重新分配。  
  
 在不能编译重新绑定的编译器中，模板实例化时所使用的 std::size_t 参数的值并不一定是传递给缓存的成员函数 allocate 和 deallocate 的 argument _Sz 值。  
  
 \<allocators> 提供以下缓存模板：  
  
- [cache_freelist](../standard-library/cache-freelist-class.md)  
  
- [cache_suballoc](../standard-library/cache-suballoc-class.md)  
  
- [cache_chunklist](../standard-library/cache-chunklist-class.md)  
  
 筛选器是一个块分配器，它使用其他块分配器（作为模板参数向其传递）执行它的成员函数。 筛选器最常见的形式是同步筛选器，它采用同步策略来控制对其他块分配器实例的成员函数的访问。 \<allocators> 提供以下同步筛选器：  
  
- [sync_none](../standard-library/sync-none-class.md)  
  
- [sync_per_container](../standard-library/sync-per-container-class.md)  
  
- [sync_per_thread](../standard-library/sync-per-thread-class.md)  
  
- [sync_shared](../standard-library/sync-shared-class.md)  
  
 \<allocators> 还提供筛选器 [rts_alloc](../standard-library/rts-alloc-class.md)它持有多个块分配器实例，并确定运行时（而非编译时）用于分配或解除分配的实例。 它与不能编译重新绑定的编译器一起使用。  
  
 同步策略确定分配器实例如何处理来自多线程的同步分配和解除分配的请求。 最简单的策略是将所有请求直接传递到基础缓存对象，将同步管理留给用户。 较复杂的策略是使用互斥体对基础缓存对象的访问进行序列化。  
  
 如果编译器支持编译单线程和多线程应用程序，则单线程应用程序的默认同步筛选器为 `sync_none`，在所有其他情况下为 `sync_shared`。  
  
 缓存模板 `cache_freelist` 采用最大类参数，它确定存储在可用的列表中元素的最大数量。  
  
 \<allocators> 提供以下 max 类：  
  
- [max_none](../standard-library/max-none-class.md)  
  
- [max_unbounded](../standard-library/max-unbounded-class.md)  
  
- [max_fixed_size](../standard-library/max-fixed-size-class.md)  
  
- [max_variable_size](../standard-library/max-variable-size-class.md)  
  
### <a name="macros"></a>宏  
  
|||  
|-|-|  
|[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)|生成一个分配器模板类。|  
|[CACHE_CHUNKLIST](../standard-library/allocators-functions.md#cache_chunklist)|生成 `stdext::allocators::cache_chunklist<sizeof(Type)>`。|  
|[CACHE_FREELIST](../standard-library/allocators-functions.md#cache_freelist)|生成 `stdext::allocators::cache_freelist<sizeof(Type), max>`。|  
|[CACHE_SUBALLOC](../standard-library/allocators-functions.md#cache_suballoc)|生成 `stdext::allocators::cache_suballoc<sizeof(Type)>`。|  
|[SYNC_DEFAULT](../standard-library/allocators-functions.md#sync_default)|生成同步筛选器。|  
  
### <a name="operators"></a>运算符  
  
|||  
|-|-|  
|[operator!= (\<allocators>)](../standard-library/allocators-operators.md#op_neq)|测试指定类的分配器对象之间是否不相等。|  
|[operator== (\<allocators>)](../standard-library/allocators-operators.md#op_eq_eq)|测试指定类的分配器对象之间是否相等。|  
  
### <a name="classes"></a>类  
  
|||  
|-|-|  
|[allocator_base](../standard-library/allocator-base-class.md)|定义基类和常用函数需要从同步筛选器创建一个用户定义的分配器。|  
|[allocator_chunklist](../standard-library/allocator-chunklist-class.md)|描述一个对象，用于管理使用缓存类型为 [cache_chunklist](../standard-library/cache-chunklist-class.md) 的对象的存储分配和释放。|  
|[allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)|描述一个对象，用于管理由 [max_fixed_size](../standard-library/max-fixed-size-class.md) 所管理的长度的使用缓存类型 [cache_suballoc](../standard-library/cache-freelist-class.md) 的类型 `Type` 的对象的存储分配和释放。|  
|[allocator_newdel](../standard-library/allocator-newdel-class.md)|实现分配器使用 `operator delete` 来释放内存块和使用 `operator new` 来分配内存块。|  
|[allocator_suballoc](../standard-library/allocator-suballoc-class.md)|描述一个对象，用于管理使用类型 [cache_suballoc](../standard-library/cache-suballoc-class.md) 的缓存类型的类型 `Type` 的对象的存储分配和释放。|  
|[allocator_unbounded](../standard-library/allocator-unbounded-class.md)|描述一个对象，用于管理使用缓存类型为 [cache_freelist](../standard-library/cache-freelist-class.md) 的对象类型 `Type` 的存储分配和释放，其长度由 [max_unbounded](../standard-library/max-unbounded-class.md) 管理。|  
|[allocator_variable_size](../standard-library/allocator-variable-size-class.md)|描述一个对象，用于管理使用缓存类型为 [cache_freelist](../standard-library/cache-freelist-class.md) 的对象类型 `Type` 的存储分配和释放，其长度由 [max_variable_size](../standard-library/max-variable-size-class.md) 管理。|  
|[cache_chunklist](../standard-library/cache-chunklist-class.md)|定义分配和释放单个大小内存块的块分配器。|  
|[cache_freelist](../standard-library/cache-freelist-class.md)|定义分配和释放单个大小内存块的块分配器。|  
|[cache_suballoc](../standard-library/cache-suballoc-class.md)|定义分配和释放单个大小内存块的块分配器。|  
|[freelist](../standard-library/freelist-class.md)|管理内存块列表。|  
|[max_fixed_size](../standard-library/max-fixed-size-class.md)|描述 max 类对象，该对象将 [freelist](../standard-library/freelist-class.md) 对象限制为固定的最大长度。|  
|[max_none](../standard-library/max-none-class.md)|描述 max 类对象，该对象将 [freelist](../standard-library/freelist-class.md) 对象限制为零的最大长度。|  
|[max_unbounded](../standard-library/max-unbounded-class.md)|描述 max 类对象，该对象不限制 [freelist](../standard-library/freelist-class.md) 对象的最大长度。|  
|[max_variable_size](../standard-library/max-variable-size-class.md)|描述 max 类对象，该对象将 [freelist](../standard-library/freelist-class.md) 对象限制为与已分配的内存块数大致成比例的最大长度。|  
|[rts_alloc](../standard-library/rts-alloc-class.md)|rts_alloc 模板类描述一种[筛选器](../standard-library/allocators-header.md)，它具有缓存实例数组，并确定运行时（而非编译时）用于分配和解除分配的实例。|  
|[sync_none](../standard-library/sync-none-class.md)|描述不提供同步的同步筛选器。|  
|[sync_per_container](../standard-library/sync-per-container-class.md)|描述为每个筛选器对象提供单独的缓存对象的同步筛选。|  
|[sync_per_thread](../standard-library/sync-per-thread-class.md)|描述为每个线程提供单独的缓存对象的同步筛选器。|  
|[sync_shared](../standard-library/sync-shared-class.md)|介绍同步筛选器，它使用互斥体来控制对所有分配器共享的缓存对象的访问。|  
  
## <a name="requirements"></a>要求  
 **标头：**\<allocators>  
  
 **命名空间：** stdext  
  
## <a name="see-also"></a>另请参阅  
 [头文件引用](../standard-library/cpp-standard-library-header-files.md)




