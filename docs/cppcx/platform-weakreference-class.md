---
title: "Platform:: weakreference 类 |Microsoft 文档"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Platform::WeakReference
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: c161bf901b0e055885858d8570925f58e2eb971a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="platformweakreference-class"></a>Platform::WeakReference 类
表示对 ref 类实例的弱引用。  
  
## <a name="syntax"></a>语法  
  
```cpp 
class WeakReference  
```  
  
#### <a name="parameters"></a>参数  
  
### <a name="members"></a>成员  
  
### <a name="constructors"></a>构造函数  
  
|成员|描述|  
|------------|-----------------|  
|[Weakreference:: Weakreference](#ctor)|初始化 WeakReference 类的新实例。|  
  
### <a name="methods"></a>方法  
  
|成员|描述|  
|------------|-----------------|  
|[Weakreference::](#resolve)|如果对象不再存在，则返回基础 ref 类的句柄或 nullptr。|  
  
### <a name="operators"></a>运算符  
  
|成员|描述|  
|------------|-----------------|  
|[WeakReference::operator=](#operator-assign)|给 WeakReference 对象赋新值。|  
|[WeakReference::operator BoolType](#booltype)|实现安全 bool 模式。|  
  
### <a name="remarks"></a>备注  
 WeakReference 类本身不是 ref 类，因此不从 Platform::Object^ 继承，也不能在公共方法的签名中使用。  

## <a name="operator-assign"></a>WeakReference::operator =
给 WeakReference 赋值。  
  
### <a name="syntax"></a>语法  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));    
WeakReference& operator=(const WeakReference& otherArg);   
WeakReference& operator=(WeakReference&& otherArg);    
WeakReference& operator=(const volatile ::Platform::Object^ const otherArg); 
```  
  
### <a name="remarks"></a>备注  
 使用上面列表中的最后一个重载，可以向 WeakReference 变量分配 ref 类。 在这种情况下，ref 类是向下转换到[platform:: object](../cppcx/platform-object-class.md)^。 还原原始类型更高版本通过指定中的类型参数的自变量作为[weakreference::\<T >](#resolve)成员函数。  
  
## <a name="booltype"></a>WeakReference::operator BoolType
实现 WeakReference 类的安全 bool 模式。 不在你的代码中显式调用。  
  
### <a name="syntax"></a>语法  
  
```cpp  
BoolType BoolType()  
```  

## <a name="resolve"></a>Weakreference:: Resolve 方法 （平台命名空间）
如果对象不再存在，则返回原始 ref 类的句柄或 `nullptr`。  
  
### <a name="syntax"></a>语法  
  
```cpp  
  
template<typename T>  
T^ Resolve() const  
```  
  
### <a name="parameters"></a>参数  
  
### <a name="property-valuereturn-value"></a>属性值/返回值  
 WeakReference 对象先前关联的 ref 类的句柄或 nullptr。  
  
### <a name="example"></a>示例  
 这是代码示例的描述。  
  
```  
  
Bar^ bar = ref new Bar();  
//use bar...  
  
if (bar != nullptr)  
{  
    WeakReference wr(bar);  
    Bar^ newReference = wr.Resolve<Bar>();  
}  
```  
  
 注意类型参数是 T 而非 T^。  
  
 
## <a name="ctor"></a>Weakreference:: Weakreference 构造函数
提供构造 WeakReference 的各种方式。  
  
### <a name="syntax"></a>语法  
  
```cpp  
WeakReference();  
WeakReference(decltype(__nullptr));  
WeakReference(const WeakReference& otherArg);  
WeakReference(WeakReference&& otherArg);  
explicit WeakReference(const volatile ::Platform::Object^ const otherArg);  
```  
### <a name="example"></a>示例  
  
```cpp    
MyClass^ mc = ref new MyClass();  
WeakReference wr(mc);  
MyClass^ copy2 = wr.Resolve<MyClass>();    
```  
  
## <a name="see-also"></a>另请参阅  
 [平台命名空间](../cppcx/platform-namespace-c-cx.md)