---
title: IDiaSymbol::findInlineFramesByAddr |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 36a122e6-f27e-40cd-9784-cdaf279e1905
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 234a9ed99f7cb980b40411bb33a9f1472d05ca24
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49827416"
---
# <a name="idiasymbolfindinlineframesbyaddr"></a>IDiaSymbol::findInlineFramesByAddr
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索一个枚举，允许客户端用于循环访问所有给定地址上的内联框架。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT findInlineFramesByAddr (   
   DWORD             isect,  
   DWORD             offset,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `isect`  
 [in]指定地址的部分组件。  
  
 `offset`  
 [in]指定地址的偏移量的部分。  
  
 `ppResult`  
 [out]保存`IDiaEnumSymbols`对象，其中包含检索到的框架的列表。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)



