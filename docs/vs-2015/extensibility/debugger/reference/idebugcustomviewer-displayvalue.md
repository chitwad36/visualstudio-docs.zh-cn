---
title: IDebugCustomViewer::DisplayValue |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCustomViewer::DisplayValue
helpviewer_keywords:
- IDebugCustomViewer::DisplayValue
ms.assetid: 7a538248-5ced-450e-97cd-13fabe35fb1c
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a96184b993a9ff2350e6424149ee3f585fbd2330
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49865019"
---
# <a name="idebugcustomviewerdisplayvalue"></a>IDebugCustomViewer::DisplayValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

调用此方法以显示指定的值。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT DisplayValue(  
   HWND             hwnd,  
   DWORD            dwID,  
   IUnknown *       pHostServices,  
   IDebugProperty3* pDebugProperty);  
);  
```  
  
```csharp  
int DisplayValue(  
   IntPtr          hwnd,   
   uint            dwID,   
   object          pHostServices,   
   IDebugProperty3 pDebugProperty  
);  
```  
  
#### <a name="parameters"></a>参数  
 `hwnd`  
 [in]父窗口  
  
 `dwID`  
 [in]支持多个类型的自定义查看器的 ID。  
  
 `pHostServices`  
 [in] 保留。 始终设置为 null。  
  
 `pDebugProperty`  
 [in]可用于检索要显示的值的接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。  
  
## <a name="remarks"></a>备注  
 显示的"modal"在于此方法将创建必要的窗口，显示的值，等待输入，并关闭窗口，然后再返回给调用方所有。 这意味着该方法必须处理的显示属性的值，从创建一个用于输出，等待用户输入，到销毁窗口的窗口的所有方面。  
  
 若要支持上更改的值给定[IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)对象，可以使用[SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)方法 — 如果值可以表示为一个字符串。 否则，将创建一个自定义接口所需 — 独占向表达式计算器实施这`DisplayValue`方法，实现对同一对象`IDebugProperty3`接口。 此自定义接口将提供用于更改数据的任意大小或复杂性的方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)

