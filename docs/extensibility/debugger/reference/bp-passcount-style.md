---
title: BP_PASSCOUNT_STYLE |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_PASSCOUNT_STYLE
helpviewer_keywords:
- BP_PASSCOUNT_STYLE structure
ms.assetid: 0a647047-e2d5-4724-a0b8-68108425ecad
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f382c83813eb794fc48e33310ba8381030b424fc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49846117"
---
# <a name="bppasscountstyle"></a>BP_PASSCOUNT_STYLE
指定将导致触发该断点的断点传递计数与相关联的条件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
typedef DWORD BP_PASSCOUNT_STYLE;  
```  
  
```csharp  
public enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
```  
  
## <a name="members"></a>成员  
 BP_PASSCOUNT_NONE  
 不指定任何断点传递计数样式。  
  
 BP_PASSCOUNT_EQUAL  
 设置为等于断点传递计数样式。 当命中断点次数等于传递计数时，将触发断点。  
  
 BP_PASSCOUNT_EQUAL_OR_GREATER  
 将断点传递计数样式设置为相等或更高版本。 当命中断点次数等于或大于传递计数时，将触发断点。  
  
 BP_PASSCOUNT_MOD  
 指定取模传递计数。 例如，如果类型是传递计数`BP_PASSCOUNT_MOD`和传递计数值为 4，断点将触发每次命中的计数是 4 的倍数。  
  
## <a name="remarks"></a>备注  
 用于`stylePassCount`的成员[BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)结构，它又是的成员[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)并[BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)结构。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)