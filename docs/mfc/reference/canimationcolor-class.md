---
title: "CAnimationColor 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
dev_langs: C++
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e03ba23b30c714216356d49086a0d8f81df7db14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="canimationcolor-class"></a>CAnimationColor 类
实现可对颜色的红色、绿色和蓝色分量进行动画处理的颜色功能。  
  
## <a name="syntax"></a>语法  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|已重载。 将构造一个动画颜色对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|为红色、 绿色和蓝色组件添加转换。|  
|[CAnimationColor::GetB](#getb)|提供对 CAnimationVariable 表示蓝色组件访问。|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|返回颜色组件的默认值。|  
|[CAnimationColor::GetG](#getg)|提供对 CAnimationVariable 表示绿色组件访问。|  
|[CAnimationColor::GetR](#getr)|提供对 CAnimationVariable 表示红色组件访问。|  
|[CAnimationColor::GetValue](#getvalue)|返回当前值。|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|设置默认值。|  
  
### <a name="protected-methods"></a>受保护的方法  
  
|名称|描述|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|将封装的动画变量放入列表。 (重写[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)。)|  
  
### <a name="public-operators"></a>公共运算符  
  
|名称|描述|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|将颜色分配给 CAnimationColor。|  
  
### <a name="protected-data-members"></a>受保护的数据成员  
  
|名称|描述|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|表示动画颜色中的蓝色部分的封装的动画变量。|  
|[CAnimationColor::m_gValue](#m_gvalue)|表示动画颜色中的绿色部分的封装的动画变量。|  
|[CAnimationColor::m_rValue](#m_rvalue)|表示动画颜色中的红色部分的封装的动画变量。|  
  
## <a name="remarks"></a>备注  
 CAnimationColor 类封装三个 CAnimationVariable 对象，并可以表示在应用程序中一种颜色。 例如，你可以使用此类进行动画处理的屏幕上的任何对象的颜色 （如文本颜色的背景颜色等）。 若要在应用程序中使用此类，只需实例化此类的对象、 将其添加到动画控制器使用 CAnimationController::AddAnimationObject 然后调用为每个转换的 AddTransition 要应用于红色、 绿色和蓝色分量。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>要求  
 **标头：** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationColor::AddTransition  
 为红色、 绿色和蓝色组件添加转换。  
  
```  
void AddTransition(
    CBaseTransition* pRTransition,  
    CBaseTransition* pGTransition,  
    CBaseTransition* pBTransition);
```  
  
### <a name="parameters"></a>参数  
 `pRTransition`  
 红色分量的转换。  
  
 `pGTransition`  
 绿色分量的转换。  
  
 `pBTransition`  
 蓝色分量的转换。  
  
### <a name="remarks"></a>备注  
 调用此函数可将指定的转换添加到转换应用于表示颜色组件的动画变量的内部列表。 添加转换时，它们都不会立即应用和存储在内部列表。 转换将应用 （添加到情节提要特定值） 时调用 CAnimationController::AnimateGroup。 如果你不需要将转换应用于颜色组件之一，则可以传递 NULL。  
  
##  <a name="canimationcolor"></a>CAnimationColor::CAnimationColor  
 构造 CAnimationColor 对象。  
  
```  
CAnimationColor();
 
CAnimationColor(
    COLORREF color,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>参数  
 `color`  
 指定默认颜色。  
  
 `nGroupID`  
 指定组 id。  
  
 `nObjectID`  
 指定对象 id。  
  
 `dwUserData`  
 指定用户定义的数据。  
  
### <a name="remarks"></a>备注  
 使用默认值为红色、 绿色和蓝色，对象 ID 和组 ID，将设置为 0 构造对象。 它们可以在运行时使用 SetDefaultValue 和 SetID 更高版本更改。  
  
##  <a name="getanimationvariablelist"></a>CAnimationColor::GetAnimationVariableList  
 将封装的动画变量放入列表。  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>参数  
 `lst`  
 当函数返回时，它包含指向表示红色、 绿色和蓝色分量的三个 CAnimationVariable 对象的指针。  
  
##  <a name="getb"></a>CAnimationColor::GetB  
 提供对 CAnimationVariable 表示蓝色组件访问。  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>返回值  
 对封装 CAnimationVariable 表示蓝色组件的引用。  
  
### <a name="remarks"></a>备注  
 你可以调用此方法以获取对基础 CAnimationVariable 表示蓝色组件的直接访问权限。  
  
##  <a name="getdefaultvalue"></a>CAnimationColor::GetDefaultValue  
 返回颜色组件的默认值。  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>返回值  
 包含 RGB 组件的默认值的 COLORREF 值。  
  
### <a name="remarks"></a>备注  
 调用此函数可检索之前已由构造函数或 SetDefaultValue 设置的默认值。  
  
##  <a name="getg"></a>CAnimationColor::GetG  
 提供对 CAnimationVariable 表示绿色组件访问。  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>返回值  
 对封装 CAnimationVariable 表示绿色组件的引用。  
  
### <a name="remarks"></a>备注  
 你可以调用此方法以获取对基础 CAnimationVariable 表示绿色组件的直接访问权限。  
  
##  <a name="getr"></a>CAnimationColor::GetR  
 提供对 CAnimationVariable 表示红色组件访问。  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>返回值  
 对封装 CAnimationVariable 表示红色组件的引用。  
  
### <a name="remarks"></a>备注  
 你可以调用此方法以获取对基础 CAnimationVariable 表示红色组件的直接访问权限。  
  
##  <a name="getvalue"></a>CAnimationColor::GetValue  
 返回当前值。  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>参数  
 `color`  
 输出。 此方法返回时包含的当前值。  
  
### <a name="return-value"></a>返回值  
 已成功检索的当前值; 如果为 TRUE否则为 FALSE。  
  
### <a name="remarks"></a>备注  
 调用此函数可检索动画颜色的当前值。 如果此方法失败或基础 COM 对象的颜色组件尚未初始化，颜色将包含在构造函数中或通过 SetDefaultValue 之前已设置的默认值。  
  
##  <a name="m_bvalue"></a>CAnimationColor::m_bValue  
 表示动画颜色中的蓝色部分的封装的动画变量。  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="m_gvalue"></a>CAnimationColor::m_gValue  
 表示动画颜色中的绿色部分的封装的动画变量。  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="m_rvalue"></a>CAnimationColor::m_rValue  
 表示动画颜色中的红色部分的封装的动画变量。  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="operator_colorref"></a>CAnimationColor::operator COLORREF  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>返回值  
  
##  <a name="operator_eq"></a>CAnimationColor::operator =  
 将颜色分配给 CAnimationColor。  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>参数  
 `color`  
 指定新值动画颜色。  
  
### <a name="remarks"></a>备注  
 建议你先执行该操作早动画开始日期，原因是此运算符将调用 SetDefaultValue，重新创建颜色组件的基础 COM 对象，如果已创建。 如果你订阅事件 （ValueChanged 或 IntegerValueChanged） 为此动画对象，你需要重新启用这些事件。  
  
##  <a name="setdefaultvalue"></a>CAnimationColor::SetDefaultValue  
 设置默认值。  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>参数  
 `color`  
 指定红色、 绿色和蓝色分量的新默认的值。  
  
### <a name="remarks"></a>备注  
 使用此函数将默认值设置为动画对象。 此方法将默认值分配给动画颜色的颜色组件。 它还重新创建基础 COM 对象，如果已创建。 如果你订阅事件 （ValueChanged 或 IntegerValueChanged） 为此动画对象，你需要重新启用这些事件。  
  
## <a name="see-also"></a>另请参阅  
 [类](../../mfc/reference/mfc-classes.md)
