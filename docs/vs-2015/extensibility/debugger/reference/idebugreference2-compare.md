---
title: IDebugReference2::Compare |Microsoft Docs
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
- IDebugReference2::Compare
helpviewer_keywords:
- IDebugReference2::Compare
ms.assetid: 3361c495-2673-4b7c-82e3-dee74e1fa58d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8f61526ac65c947af47bf278029f9f80d72b9a3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479301"
---
# <a name="idebugreference2compare"></a>IDebugReference2::Compare
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugReference2::Compare](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugreference2-compare)。  
  
比较对另一个引用。 留待将来使用。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Compare (   
   REFERENCE_COMPARE dwCompare,  
   IDebugReference2* pReference  
);  
```  
  
```csharp  
int Compare (   
   enum_REFERENCE_COMPARE dwCompare,  
   IDebugReference2       pReference  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwCompare`  
 [in]中的值[REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md)枚举，用于指定的比较操作，例如，等于、 小于或大于。  
  
 `pReference`  
 [in][IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)对象，表示要进行比较的引用。  
  
## <a name="return-value"></a>返回值  
 始终返回 `E_NOTIMPL`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md)
