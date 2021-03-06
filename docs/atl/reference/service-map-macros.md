---
title: "服务映射宏 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: eea45a3315237c77eff0231d485111cefb8557cc
ms.contentlocale: zh-cn
ms.lasthandoff: 02/24/2017

---
# <a name="service-map-macros"></a>服务映射宏
这些宏定义服务映射和条目。  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|标记 ATL 服务映射的开头。|  
|[END_SERVICE_MAP](#end_service_map)|将标记 ATL 服务映射的结尾。|  
|[SERVICE_ENTRY](#service_entry)|该值指示对象支持特定的服务 id。|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|指示[IServiceProviderImpl::QueryService](#queryservice)链接到指定的对象。|  

## <a name="requirements"></a>要求  
 **标头︰** atlcom.h  
   
##  <a name="begin_service_map"></a>BEGIN_SERVICE_MAP  
 标记服务映射的开头。  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>参数  
 `theClass`  
 [in]指定包含服务映射的类。  
  
### <a name="remarks"></a>备注  
 使用服务映射对 COM 对象实现的服务提供程序功能。 首先，必须派生您的类从[IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)。 有两种类型的条目︰  
  
- [SERVICE_ENTRY](#service_entry)指示支持指定的服务 ID (SID)。  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain) Instructs [IServiceProviderImpl::QueryService](#queryservice)链接到另一个指定的对象。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_ATL_COM&#57;](../../atl/codesnippet/cpp/service-map-macros_1.h)]  
  
##  <a name="end_service_map"></a>END_SERVICE_MAP  
 将服务映射的结尾标记。  
  
```
END_SERVICE_MAP()
```  
  
### <a name="example"></a>示例  
 请参阅示例[BEGIN_SERVICE_MAP](#begin_service_map)。  
  
##  <a name="service_entry"></a>SERVICE_ENTRY  
 该值指示对象是否支持指定的服务 id *SID*。  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>参数  
 *SID*  
 服务 id。  
  
### <a name="example"></a>示例  
 请参阅示例[BEGIN_SERVICE_MAP](#begin_service_map)。  
  
##  <a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN  
 指示[IServiceProviderImpl::QueryService](#queryservice)链接到指定的对象`punk`。  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>参数  
 `punk`  
 一个指向**IUnknown**接口链。  
  
### <a name="example"></a>示例  
 请参阅示例[BEGIN_SERVICE_MAP](#begin_service_map)。  
  
##  <a name="queryservice"></a>IServiceProviderImpl::QueryService  
 创建或访问指定的服务并返回服务的指定接口的接口指针。  
  
```
STDMETHOD(QueryService)( 
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>参数  
 [IN]`guidService`  
 为服务标识符 (SID) 的指针。  
  
 [IN]`riid`  
 调用方是访问接口的标识符。  
  
 [OUT]`ppvObj`  
 指向所请求的接口的间接指针。  
  
### <a name="return-value"></a>返回值  
 返回`HRESULT`值是以下之一︰  
  
|返回值|含义|  
|------------------|-------------|  
|S_OK|该服务已成功创建或检索。|  
|E_INVALIDARG|一个或多个参数无效。|  
|E_OUTOFMEMORY|内存不足，无法创建服务。|  
|E_UNEXPECTED|发生未知错误。|  
|E_NOINTERFACE|所请求的接口不是此服务的一部分，或者服务未知。|  
  
### <a name="remarks"></a>备注  
 `QueryService`返回对指定服务中请求的接口的间接指针。 调用方负责在不再需要释放此指针。  
  
 当您调用`QueryService`，传递两个服务标识符 ( `guidService`) 和接口标识符 ( `riid`)。 `guidService`指定访问权限，要向其中的服务和`riid`标识是服务的一部分的接口。 作为回报，您将收到间接指向的接口。  
  
 实现该接口的对象也可能实现属于其他服务的接口。 考虑以下情况：  
  
-   这些接口的一些可能是可选的。 并非所有在服务说明中定义的接口都需要出现或每个返回的对象上每个服务实现。  
  
-   与不同的是对调用`QueryInterface`，传递不同的服务标识符并不一定意味着将返回一个不同的组件对象模型 (COM) 对象。  
  
-   返回的对象可能具有不是服务定义的一部分的其他接口。  
  
 两个不同的服务，如 SID_SMyService 和 SID_SYourService，可以同时指定使用同一个接口，即使接口的实现可能具有两个服务之间的共同点没有任何内容。 此方法有效，因为调用`QueryService`（SID_SMyService、 IID_IDispatch） 可以返回不同的对象比`QueryService`（SID_SYourService、 IID_IDispatch）。 指定一个不同的服务标识符时，将不会假定对象标识。  
  
## <a name="see-also"></a>另请参阅  
 [宏](../../atl/reference/atl-macros.md)

