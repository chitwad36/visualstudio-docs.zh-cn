---
title: “监视”命令 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.watch
helpviewer_keywords:
- Watch command
- Debug.Watch command
ms.assetid: aa02e647-d9f5-4905-a651-52a8df595795
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9b1d5a1a1ffac1c67b5a3a1e1ad4a860c6b2ad4f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49214352"
---
# <a name="watch-command"></a>“监视”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
创建并打开指定“监视”  窗口的实例。 可使用“监视”窗口计算变量、表达式或寄存器的值，然后编辑这些值并保存结果。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.Watch[index]  
```  
  
## <a name="arguments"></a>自变量  
 `index`  
 必须的。 监视窗口的实例数。  
  
## <a name="remarks"></a>备注  
 `index` 必须为整数。 有效值为 1、2、3 或 4。  
  
## <a name="example"></a>示例  
  
```  
>Debug.Watch1  
```  
  
## <a name="see-also"></a>请参阅  
 [“自动”和“局部变量”窗口](../../debugger/autos-and-locals-windows.md)   
 [如何： 编辑变量窗口中的值](http://msdn.microsoft.com/library/36f464ab-c900-4c0b-9ab3-557b3d9cdab5)   
 [如何： 使用快速监视对话框](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



