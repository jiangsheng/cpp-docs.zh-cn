---
title: "CNetAddressCtrl 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
dev_langs: C++
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 047032e65f0d1fa7847caae36e10fac4175b5db0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2017
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl 类
`CNetAddressCtrl` 类表示网络地址控件，可使用此控件输入和验证 IPv4、IPv6 与命名的 DNS 地址的格式。  
  
## <a name="syntax"></a>语法  
  
```  
class CNetAddressCtrl : public CEdit  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|构造 `CNetAddressCtrl` 对象。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CNetAddressCtrl::Create](#create)|创建具有指定样式的网络地址控件并将其附加到当前`CNetAddressCtrl`对象。|  
|[CNetAddressCtrl::CreateEx](#createex)|指定的扩展样式创建的网络地址控件，并将其附加到当前`CNetAddressCtrl`对象。|  
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|当用户在当前的网络地址控件中输入一个不受支持的网络地址，则显示错误气球状提示。|  
|[CNetAddressCtrl::GetAddress](#getaddress)|检索与当前的网络地址控件关联的网络地址的验证，并且已分析表示。|  
|[CNetAddressCtrl::GetAllowType](#getallowtype)|检索当前的网络地址控件可以支持的网络地址的类型。|  
|[CNetAddressCtrl::SetAllowType](#setallowtype)|设置当前的网络地址控件可以支持的网络地址的类型。|  
  
## <a name="remarks"></a>备注  
 网络地址控件验证用户输入的地址的格式正确。 控件不实际连接到的网络地址。 [CNetAddressCtrl::SetAllowType](#setallowtype)方法指定的地址的一个或多个类型的[CNetAddressCtrl::GetAddress](#getaddress)方法可以分析和验证。 地址可以是 IPv4、 IPv6，或服务器、 网络、 主机或广播的消息目标的命名的地址的形式。 如果该地址的格式不正确，则可以使用[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)显示信息提示消息框以图形方式指向的网络地址控件的文本框中，并显示一个预定义的方法错误消息。  
  
 `CNetAddressCtrl`类派生自[CEdit](../../mfc/reference/cedit-class.md)类。 因此，网络地址控件提供 Windows 编辑控件的所有消息的访问。  
  
 下图描绘了一个对话框，其中包含网络地址控件。 文本框 （1） 的网络地址控件包含一个无效的网络地址。 如果网络地址无效，将显示信息提示消息 (2)。  
  
 ![具有网络地址控件和信息提示的对话框。] (../../mfc/reference/media/cnetaddctrl.png "cnetaddctrl")  
  
## <a name="example"></a>示例  
 下面的代码示例是对话框，用于验证的网络地址的一部分。 三个单选按钮的事件处理程序指定的网络地址可以是三种地址类型之一。 用户在文本框中的网络控件中，输入地址，然后按下按钮来验证地址。 如果地址是否有效，将显示一条成功消息;否则，会显示预定义的信息提示错误消息。  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]  
  
## <a name="example"></a>示例  
 下面的代码示例来自对话框标头文件定义[NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345)和[NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346)变量所需的[CNetAddressCtrl::GetAddress](#getaddress)方法。  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CNetAddressCtrl`  
  
## <a name="requirements"></a>要求  
 **标头：** afxcmn.h  
  
 此类支持在[!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]及更高版本。  
  
 此类的其他要求中所述[生成要求的 Windows Vista 公共控件](../../mfc/build-requirements-for-windows-vista-common-controls.md)。  
  
##  <a name="cnetaddressctrl"></a>CNetAddressCtrl::CNetAddressCtrl  
 构造 `CNetAddressCtrl` 对象。  
  
```  
CNetAddressCtrl();
```  
  
### <a name="remarks"></a>备注  
 使用[CNetAddressCtrl::Create](#create)或[CNetAddressCtrl::CreateEx](#createex)方法来创建网络控件并将其附加到`CNetAddressCtrl`对象。  
  
##  <a name="create"></a>CNetAddressCtrl::Create  
 创建具有指定样式的网络地址控件并将其附加到当前`CNetAddressCtrl`对象。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>参数  
  
|参数|说明|  
|---------------|-----------------|  
|[in] `dwStyle`|要应用于控件的样式按位组合。 有关详细信息，请参阅[编辑样式](../../mfc/reference/styles-used-by-mfc.md#edit-styles)。|  
|[in] `rect`|对引用[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)结构，其中包含的位置和大小的控件。|  
|[in] `pParentWnd`|指向的非 null 指针[CWnd](../../mfc/reference/cwnd-class.md)是控件的父窗口的对象。|  
|[in] `nID`|控件的 ID。|  
  
### <a name="return-value"></a>返回值  
 如果此方法成功，则为 `true`；否则为 `false`。  
  
##  <a name="createex"></a>CNetAddressCtrl::CreateEx  
 指定的扩展样式创建的网络地址控件，并将其附加到当前`CNetAddressCtrl`对象。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>参数  
  
|参数|说明|  
|---------------|-----------------|  
|[in] `dwExStyle`|若要应用于控件的扩展样式按位组合 (OR)。 有关详细信息，请参阅`dwExStyle`参数[CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)函数。|  
|[in] `dwStyle`|要应用于控件的样式按位组合 (OR)。 有关详细信息，请参阅[编辑样式](../../mfc/reference/styles-used-by-mfc.md#edit-styles)。|  
|[in] `rect`|对引用[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)结构，其中包含的位置和大小的控件。|  
|[in] `pParentWnd`|指向的非 null 指针[CWnd](../../mfc/reference/cwnd-class.md)是控件的父窗口的对象。|  
|[in] `nID`|控件的 ID。|  
  
### <a name="return-value"></a>返回值  
 如果此方法成功，则为 `true`；否则为 `false`。  
  
##  <a name="displayerrortip"></a>CNetAddressCtrl::DisplayErrorTip  
 与当前的网络地址控件相关联的气球状提示中显示一条错误消息。  
  
```  
HRESULT DisplayErrorTip();
```  
  
### <a name="return-value"></a>返回值  
 值`S_OK`如果此方法成功; 否则为错误代码。  
  
### <a name="remarks"></a>备注  
 使用[CNetAddressCtrl::SetAllowType](#setallowtype)方法，以指定当前的网络地址控件可以支持的地址的类型。 使用[CNetAddressCtrl::GetAddress](#getaddress)方法来验证和分析用户输入的网络地址。 使用[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)方法以显示错误消息信息提示，如果[CNetAddressCtrl::GetAddress](#getaddress)方法不成功。  
  
 此消息时，将调用[NetAddr_DisplayErrorTip](http://msdn.microsoft.com/library/windows/desktop/bb774314)宏，Windows SDK 中介绍。 该宏将发送`NCM_DISPLAYERRORTIP`消息。  
  
##  <a name="getaddress"></a>CNetAddressCtrl::GetAddress  
 检索与当前的网络地址控件相关联的网络地址的验证，并且已分析表示。  
  
```  
HRESULT GetAddress(PNC_ADDRESS pAddress) const;  
```  
  
### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|[in, out] `pAddress`|指向[NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345)结构。  设置`pAddrInfo`到的地址此结构的成员[NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346)结构，然后才能调用 GetAddress 方法。|  
  
### <a name="return-value"></a>返回值  
 值`S_OK`如果此方法成功; 否则为 COM 错误代码。 有关可能的错误代码的详细信息，请参阅的返回值部分[NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316)宏。  
  
### <a name="remarks"></a>备注  
 如果此方法成功， [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346)结构包含有关网络地址的其他信息。  
  
 使用[CNetAddressCtrl::SetAllowType](#setallowtype)方法，以指定的地址，则当前的网络地址控件可以支持的类型。 使用[CNetAddressCtrl::GetAddress](#getaddress)方法来验证和分析用户输入的网络地址。 使用[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)方法以显示错误消息信息提示，如果[CNetAddressCtrl::GetAddress](#getaddress)方法不成功。  
  
 此方法调用[NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316)宏，Windows SDK 中介绍。 该宏将发送`NCM_GETADDRESS`消息。  
  
##  <a name="getallowtype"></a>CNetAddressCtrl::GetAllowType  
 检索当前的网络地址控件可以支持的网络地址的类型。  
  
```  
DWORD GetAllowType() const;  
```  
  
### <a name="return-value"></a>返回值  
 网络地址控件可支持的按位组合 (OR) 的标志，用于指定的地址类型。 有关详细信息，请参阅[NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586)。  
  
### <a name="remarks"></a>备注  
 此消息时，将调用[NetAddr_GetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774318)宏，Windows SDK 中介绍。 该宏将发送`NCM_GETALLOWTYPE`消息。  
  
##  <a name="setallowtype"></a>CNetAddressCtrl::SetAllowType  
 设置当前的网络地址控件可以支持的网络地址的类型。  
  
```  
HRESULT SetAllowType(DWORD dwAddrMask);
```  
  
### <a name="parameters"></a>参数  
  
|参数|说明|  
|---------------|-----------------|  
|[in] `dwAddrMask`|网络地址控件可支持的按位组合 (OR) 的标志，用于指定的地址类型。 有关详细信息，请参阅[NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586)。|  
  
### <a name="return-value"></a>返回值  
 `S_OK`如果此方法成功，则否则为 COM 错误代码。  
  
### <a name="remarks"></a>备注  
 使用[CNetAddressCtrl::SetAllowType](#setallowtype)方法，以指定当前的网络地址控件可以支持的地址的类型。 使用[CNetAddressCtrl::GetAddress](#getaddress)方法来验证和分析用户输入的网络地址。 使用[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)方法以显示错误消息信息提示，如果[CNetAddressCtrl::GetAddress](#getaddress)方法不成功。  
  
 此消息时，将调用[NetAddr_SetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774320)宏，Windows SDK 中介绍。 该宏将发送`NCM_SETALLOWTYPE`消息。  
  
## <a name="see-also"></a>另请参阅  
 [CNetAddressCtrl 类](../../mfc/reference/cnetaddressctrl-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [CEdit 类](../../mfc/reference/cedit-class.md)
