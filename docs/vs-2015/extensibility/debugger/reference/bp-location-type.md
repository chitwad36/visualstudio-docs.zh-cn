---
title: BP_LOCATION_TYPE |Microsoft Docs
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
- BP_LOCATION_TYPE
helpviewer_keywords:
- BP_LOCATION_TYPE structure
ms.assetid: 0248430a-3b61-4809-87a9-e9b6bb7d1130
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d84cb1f79a86de5ad9c9865fcea6a0f46171d7b4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49909703"
---
# <a name="bplocationtype"></a>BP_LOCATION_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

指定断点请求断点的位置类型。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
typedef DWORD BP_LOCATION_TYPE;  
```  
  
```csharp  
public enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
```  
  
## <a name="members"></a>成员  
 BPLT_NONE  
 指定没有断点位置。  
  
 BPLT_FILE_LINE  
 指定为文件行断点的位置类型。  
  
 BPLT_FUNC_OFFSET  
 指定断点的位置类型作为函数偏移量。  
  
 BPLT_CONTEXT  
 作为上下文中指定断点位置的类型。  
  
 BPLT_STRING  
 以字符串形式指定断点的位置类型。  
  
 BPLT_ADDRESS  
 指定为一个地址断点的位置类型。  
  
 BPLT_RESOLUTION  
 指定断点的位置类型来解决此问题。  
  
 BPLT_CODE_FILE_LINE  
 作为源代码的行中指定断点位置的类型。  
  
 BPLT_CODE_FUNC_OFFSET  
 为代码函数偏移量为指定断点位置的类型。  
  
 BPLT_CODE_CONTEXT  
 指定断点的位置类型作为代码上下文。  
  
 BPLT_CODE_STRING  
 为代码字符串中指定断点位置的类型。  
  
 BPLT_CODE_ADDRESS  
 为代码地址指定断点的位置类型。  
  
 BPLT_DATA_STRING  
 数据字符串形式指定断点的位置类型。  
  
 BPLT_TYPE_MASK  
 指定的位掩码，以便可以从值中提取断点类型。  
  
 BPLT_LOCATION_TYPE_MASK  
 指定的位掩码，以便可以从值中提取断点位置类型。  
  
## <a name="remarks"></a>备注  
 作为参数传递给[GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)方法。  
  
 断点位置类型组成的断点类型和位置类型。 这意味着断点位置类型永远不会是只需断点类型 (例如， `BPT_CODE`) 或位置类型 (例如， `BPLT_FILE_LINE`)。 此枚举中包含有关当前支持的所有断点位置类型预定义的常量 (`BPLT_CODE_FILE_LINE`通过`BPLT_DATA_STRING`)。  
  
 `BPT_CODE` 并`BPT_DATA`属于[BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)枚举。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)   
 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)

