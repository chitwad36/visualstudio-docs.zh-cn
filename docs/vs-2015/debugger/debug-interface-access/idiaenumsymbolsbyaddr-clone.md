---
title: 'Idiaenumsymbolsbyaddr:: Clone |Microsoft Docs'
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
helpviewer_keywords:
- IDiaEnumSymbolsByAddr::Clone method
ms.assetid: f4582c69-bc3f-4a26-bcca-b641102b85fe
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 10aaff016d595a49cca18adfbfe934cdeda76e42
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49895088"
---
# <a name="idiaenumsymbolsbyaddrclone"></a>IDiaEnumSymbolsByAddr::Clone
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

创建一个对象的副本。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Clone (   
   IDiaEnumSymbolsByAddr** ppenum  
);  
```  
  
#### <a name="parameters"></a>参数  
 ppenum  
 [out]返回[IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)对象，其中包含重复的枚举器。 未复制符号，仅枚举器。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)



