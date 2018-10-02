---
title: DOCCONTEXT_COMPARE |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DOCCONTEXT_COMPARE
helpviewer_keywords:
- DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1a4643a525e5a97f7c8af3be2e86eba9ac161936
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483098"
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[DOCCONTEXT_COMPARE](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/doccontext-compare)。  
  
指定用于比较两个文档上下文的条件。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
typedef DWORD DOCCONTEXT_COMPARE;  
```  
  
```csharp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
```  
  
## <a name="members"></a>成员  
 DOCCONTEXT_EQUAL  
 在列表中，它等于目标文档上下文中找到的第一个文档上下文。  
  
 DOCCONTEXT_LESS_THAN  
 小于目标文档上下文在列表中找到的第一个文档上下文。  
  
 DOCCONTEXT_GREATER_THAN  
 大于目标文档上下文在列表中找到的第一个文档上下文。  
  
 DOCCONTEXT_SAME_DOCUMENT  
 在目标文档上下文与在同一文档中的列表中找到的第一个文档上下文。  
  
## <a name="remarks"></a>备注  
 作为参数传递[比较](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)方法。  
  
 这些值用于指定用于在列表中查找第一个文档上下文比较条件。 文档上下文提供的文档上下文列表来比较本身对通过`IDebugDocumentContext2::Compare`方法。 为其所比较运算符列表中的第一个文档上下文`true`然后返回。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)
