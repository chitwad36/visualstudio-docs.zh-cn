---
title: ASP.NET 调试： 系统要求 |Microsoft Docs
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
- debugging ASP.NET Web applications, system requirements
- debugging ASP.NET Web applications, security requirements
ms.assetid: 7810b9b2-debf-4271-8fc7-1df031123255
caps.latest.revision: 41
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f57cdfc52079a11bfb3bd83baa2e3ff2484d368f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49286476"
---
# <a name="aspnet-debugging-system-requirements"></a>ASP.NET 调试：系统要求
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题描述了 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 调试方案的软件和安全性要求：  
  
-   本地调试：其中， [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 和 Web 应用程序在同一台计算机上运行。 此方案有两种版本：  
  
    -   [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 代码驻留在文件系统中。  
  
    -   [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 代码驻留在 IIS 网站中。  
  
-   远程调试：其中，[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 在客户端计算机上运行，并对在远程服务器计算机上运行的 Web 应用程序进行调试。  
  
## <a name="security-requirements"></a>安全性要求  
 对于远程调试，本地和远程计算机必须位于域设置或工作组设置上。  
  
 若要调试 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 辅助进程，您必须具有调试该进程的权限。 默认情况下， [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 应用程序以 **“ASPNET”** 用户身份运行。 如果辅助进程作为 **“ASPNET”** 或 **“NETWORK SERVICE”** 运行，则您必须具有管理员特权才能对它进行调试。  
  
 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 辅助进程的名称根据调试方案和 IIS 版本的不同而不同。 有关详细信息，请参阅 [How to: Find the Name of the ASP.NET Process](../debugger/how-to-find-the-name-of-the-aspnet-process.md)。  
  
 可以通过编辑运行 IIS 的服务器上的 machine.config 文件来更改用于运行 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 辅助进程的用户帐户。 实现此目的的最佳方式是使用 **“Internet 信息服务(IIS)管理器”**。 有关详细信息，请参阅[如何： 运行辅助进程以用户帐户](../debugger/how-to-run-the-worker-process-under-a-user-account.md)。  
  
 如果将 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 辅助进程更改为在您自己的用户帐户下运行，则您不必是运行 IIS 的服务器上的管理员。  
  
> [!CAUTION]
>  在将 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 辅助进程更改为使用其他帐户运行之前，应考虑如果 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 辅助进程在使用该帐户运行时会受到攻击，将可能出现哪些后果。 ASPNET 和 NETWORK SERVICE 用户帐户以最低的权限运行，从而降低了进程受到攻击时可能造成的损坏程度。 如果必须将 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 辅助进程更改为使用具有较高权限的帐户运行，则会增大受损的可能性。  
  
## <a name="see-also"></a>请参阅  
 [调试 ASP.NET 和 AJAX 应用程序](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [如何：在用户帐户下运行辅助进程](../debugger/how-to-run-the-worker-process-under-a-user-account.md)



