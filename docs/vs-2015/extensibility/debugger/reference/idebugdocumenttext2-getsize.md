---
title: IDebugDocumentText2::GetSize |Microsoft Docs
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
- IDebugDocumentText2::GetSize
helpviewer_keywords:
- IDebugDocumentText2::GetSize
ms.assetid: bf515a8f-dcee-4004-8f81-543d547ceaae
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 570ec02c2e4df7d2af9b175e6fa1c41dcd82ac8e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49906359"
---
# <a name="idebugdocumenttext2getsize"></a>IDebugDocumentText2::GetSize
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

检索在此位置上的文档中的文本的大小。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetSize(   
   ULONG* pcNumLines,  
   ULONG* pcNumChars  
);  
```  
  
```csharp  
int GetSize(   
   ref uint pcNumLines,  
   ref uint pcNumChars  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pcNumLines`  
 [out]返回文本的行数。  
  
 `pcNumChars`  
 [out]返回文本的字符数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 [C + +]如果不需要特定的值，请将传递该参数为 NULL。  
  
 [仅限 C#]必须指定这两个参数。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)

