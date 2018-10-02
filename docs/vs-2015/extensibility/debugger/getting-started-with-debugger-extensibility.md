---
title: 调试器可扩展性入门 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- getting started, Debugging SDK
- debugging [Debugging SDK], getting started
- Debugging SDK, getting started
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f8f056ed8fff53eb166b37f2adba9daa17f12916
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479427"
---
# <a name="getting-started-with-debugger-extensibility"></a>调试器可扩展性入门
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[调试器可扩展性入门](https://docs.microsoft.com/visualstudio/extensibility/debugger/getting-started-with-debugger-extensibility)。  
  
[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)]提供的信息，必须具有创建和自定义用于调试程序中的调试器组件[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]环境。  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 调试已添加派生自上以前执行的测试的广泛可用性改进[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]调试器。 可以使用[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]调试单步执行的多语言应用程序，也可以实现实时上调试应用程序和多语言解决方案时编辑的变量。  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 调试是执行的进程外与正在调试的程序，因此在应用程序的进程空间中较少受侵入。 因此，它是更轻松地编写与调试器的交互的组件，而不会影响调试程序。  
  
 最大效用[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)]，您应熟悉以下：  
  
-   [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]集成的开发环境 (IDE)  
  
-   C + + 编程语言  
  
-   ATL COM  
  
## <a name="in-this-section"></a>本节内容  
 [扩展调试器的路线图](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)  
 概述了实现在您的产品，具体取决于您的编译器和其输出中进行调试的过程。  
  
 [调试器组件](../../extensibility/debugger/debugger-components.md)  
 提供的概述[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]调试组件，包括调试引擎 (DE)、 表达式计算器 (EE) 和符号处理程序 (SH)。  
  
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)  
 描述调试的主要体系结构概念。  
  
 [调试器上下文](../../extensibility/debugger/debugger-contexts.md)  
 介绍了调试引擎 (DE) 的运行方式同时代码、 文档和表达式计算上下文中。 描述的每个三个上下文、 位置、 位置或评估与它相关。  
  
 [调试任务](../../extensibility/debugger/debugging-tasks.md)  
 包含指向不同的调试任务，如启动程序和计算表达式。
