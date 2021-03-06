---
title: "Microsoft::WRL::Details 命名空间 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Microsoft::WRL::Details 命名空间
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```  
namespace Microsoft::WRL::Details;  
```  
  
## <a name="members"></a>成员  
  
### <a name="classes"></a>类  
  
|名称|描述|  
|----------|-----------------|  
|[ComPtrRef 类](../windows/comptrref-class.md)|表示对 ComPtr 类型的对象的引用 \< T>。|  
|[ComPtrRefBase 类](../windows/comptrrefbase-class.md)|表示类的基类 [ComPtrRef](../windows/comptrref-class.md) 类。|  
|[DontUseNewUseMake 类](../windows/dontusenewusemake-class.md)|可防止使用运算符 `new` 中 `RuntimeClass`。 因此，必须使用 [使函数](../windows/make-function.md) 相反。|  
|[EventTargetArray 类](../windows/eventtargetarray-class.md)|表示事件处理程序的一个数组。|  
|[MakeAllocator 类](../windows/makeallocator-class.md)|可激活的类，无论有弱引用支持，为分配内存。|  
|[ModuleBase 类](../windows/modulebase-class.md)|表示类的基类 [模块](../windows/module-class.md) 类。|  
|[RemoveIUnknown 类](../windows/removeiunknown-class.md)|创建类型的指针，它等效于 `IUnknown`的基的类型，但具有非虚拟 `QueryInterface`, ，`AddRef`, ，和 `Release` 方法。|  
|[WeakReference 类](../windows/weakreference-class1.md)|表示 *弱引用* 可以与 Windows 运行时或经典 COM 使用 弱引用表示可能可访问或可能不可访问的对象。|  
  
### <a name="structures"></a>结构  
  
|名称|描述|  
|----------|-----------------|  
|[ArgTraits 结构](../windows/argtraits-structure.md)|接口和匿名成员函数的指定个数的参数声明指定的委托。|  
|[ArgTraitsHelper 结构](../windows/argtraitshelper-structure.md)|可帮助定义委托参数的共同的特征。|  
|[BoolStruct 结构](../windows/boolstruct-structure.md)|定义是否 ComPtr 管理接口的对象生存期。 内部使用 BoolStruct [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) 运算符。|  
|[CreatorMap 结构](../windows/creatormap-structure.md)|包含有关如何初始化、 注册和注销对象的信息。|  
|[DerefHelper 结构](../windows/derefhelper-structure.md)|表示指向的取消引用的指针 `T*` 模板参数。|  
|[EnableIf 结构](../windows/enableif-structure.md)|定义指定如果第一个模板参数的计算结果为第二个模板参数的类型的数据成员 `true`。|  
|[FactoryCache 结构](../windows/factorycache-structure.md)|包含的类工厂和用于标识已注册的值的位置 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 或 COM 类对象。|  
|[ImplementsBase 结构](../windows/implementsbase-structure.md)|用来验证中的模板参数类型 [Implements 结构](../windows/implements-structure.md)。|  
|[ImplementsHelper 结构](../windows/implementshelper-structure.md)|帮助实现 [实现](../windows/implements-structure.md) 结构。|  
|[InterfaceList 结构](../windows/interfacelist-structure.md)|用于创建递归的一组接口。|  
|[InterfaceListHelper 结构](../windows/interfacelisthelper-structure.md)|生成 `InterfaceList` 以递归方式将应用指定的模板参数的参数类型。|  
|[InterfaceTraits 结构](../windows/interfacetraits-structure.md)|接口的实现共同的特征。|  
|[InvokeHelper 结构](../windows/invokehelper-structure.md)|提供根据指定的数量和类型的参数的 invoke （） 方法的实现。|  
|[IsBaseOfStrict 结构](../windows/isbaseofstrict-structure.md)|测试一种类型是否是另一种类型的基类。|  
|[IsSame 结构](../windows/issame-structure.md)|一个指定类型等同于另一个测试指定的类型。|  
|[Nil 结构](../windows/nil-structure.md)|用来指示未指定可选的模板参数。|  
|[RemoveReference 结构](../windows/removereference-structure.md)|去除从指定的类模板参数的引用或右值引用的特性。|  
|[RuntimeClassBase 结构](../windows/runtimeclassbase-structure.md)|用于检测 `RuntimeClass` 中 [使](../windows/make-function.md) 函数。|  
|[RuntimeClassBaseT 结构](../windows/runtimeclassbaset-structure.md)|提供了用于帮助器方法 `QueryInterface` 操作和获取的接口 Id。|  
|[VerifyInheritanceHelper 结构](../windows/verifyinheritancehelper-structure.md)|测试是否有一个接口派生自另一个接口。|  
|[VerifyInterfaceHelper 结构](../windows/verifyinterfacehelper-structure.md)|验证模板参数指定的接口满足某些要求。|  
  
### <a name="enumerations"></a>枚举  
  
|名称|描述|  
|----------|-----------------|  
|[AsyncStatusInternal 枚举](../windows/asyncstatusinternal-enumeration.md)|指定状态的异步操作的内部枚举之间的映射和 **Windows::Foundation::AsyncStatus** 枚举。|  
  
### <a name="functions"></a>函数  
  
|名称|描述|  
|----------|-----------------|  
|[ActivationFactoryCallback 函数](../windows/activationfactorycallback-function.md)|获取指定的激活 id。 激活工厂|  
|[Move 函数](../windows/move-function.md)|将指定的参数从一个位置移动到另一个。|  
|[RaiseException 函数](../windows/raiseexception-function.md)|引发调用线程中的异常。|  
|[Swap 函数 （Windows 运行时 c + + 模板库）](../windows/swap-function-windows-runtime-cpp-template-library.md)|交换两个指定参数的值。|  
|[TerminateMap 函数](../windows/terminatemap-function.md)|关闭指定的模块中的类工厂。|  
  
## <a name="requirements"></a>要求  
 **标头︰** async.h、 client.h、 corewrappers.h、 event.h、 ftm.h、 implements.h、 internal.h、 module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>另请参阅  
 [Microsoft:: wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [Microsoft::WRL::Wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)