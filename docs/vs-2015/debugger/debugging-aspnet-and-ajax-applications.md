---
title: 调试 ASP.NET 和 AJAX 应用程序 |Microsoft Docs
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
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, WCF
- debugging ASP.NET Web applications
- debugging [ASP.NET], about ASP.NET debugging
- WCF, debugging
ms.assetid: 9d531913-541b-47b8-864d-138021fca0c6
caps.latest.revision: 34
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f5943b75513394b44d88dfcfa496e56dad267171
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49205200"
---
# <a name="debugging-aspnet-and-ajax-applications"></a>调试 ASP.NET 和 AJAX 应用程序
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

调试 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Web 应用程序类似于调试 Windows 窗体或任何其他 Windows 应用程序，因为这两种应用程序都涉及到控件和事件。 但是，Web 应用程序与 Windows 应用程序之间还有一些基本差异：  
  
-   在 Web 应用程序中跟踪状态更为复杂。  
  
-   在 Windows 应用程序中，要调试的代码几乎全部位于一个位置；而在 Web 应用程序中，该代码可以分别位于客户端和服务器上。 虽然 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 代码全都在服务器上，但在客户端上可能还有 JavaScript 或 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 代码。  
  
## <a name="in-this-section"></a>本节内容  
 [调试 ASP.NET 的准备工作](../debugger/preparing-to-debug-aspnet.md)  
 描述启用 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 应用程序调试所需的步骤。  
  
 [调试 Web 应用程序](../debugger/debugging-web-applications.md)  
 讨论如何调试 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 应用程序，包括启用 AJAX 的脚本应用程序。  
  
## <a name="related-sections"></a>相关章节  
 [管理调试器的异常](../debugger/managing-exceptions-with-the-debugger.md)  
 说明调试 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 异常时必须启用“仅我的代码”的原因。  
  
 [Debugging and Tracing Ajax Applications Overview](http://msdn.microsoft.com/library/92684ea0-7bb4-4a34-9203-3aa6394ce375)  
 讨论可帮助你调试 AJAX 代码的一些方法和工具。  
  
 [IntelliTrace](../debugger/intellitrace.md)  
 使用 IntelliTrace 可记录和评审应用程序的状态的历史记录而不用经常重新启动应用程序，从而加快了代码的调试速度。 您可以查看有关在运行应用程序期间发生的事件和调用的信息，然后在这些时间点上开始调试。 需要 Visual Studio Ultimate。  
  
## <a name="see-also"></a>请参阅  
 [调试器安全](../debugger/debugger-security.md)   
 [Debugging Web Applications and Script](../debugger/debugging-web-applications-and-script.md) （调试 Web 应用程序和脚本）  
 [调试器设置和准备](../debugger/debugger-settings-and-preparation.md)   
 [调试器基础知识](../debugger/debugger-basics.md)



