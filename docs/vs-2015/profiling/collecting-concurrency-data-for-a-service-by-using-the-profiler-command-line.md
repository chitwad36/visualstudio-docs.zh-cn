---
title: 使用探查器命令行收集服务的并发数据 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 275aacba-b2af-4d34-8931-ee30d777a256
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a783c30c575bbf2f55b4c31840392e7e213940e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49250973"
---
# <a name="collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line"></a>使用探查器命令行收集服务的并发数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具的并发方法可用于收集资源争用数据和线程活动数据，后者可显示 CPU 使用率、线程争用、线程迁移、同步延迟、重叠 IO 的区域和其他系统事件。  
  
> [!NOTE]
>  Windows 8 和 Windows Server 2012 中增强的安全功能需要以 Visual Studio 探查器在这些平台上收集数据的方式进行重大更改。 Windows 应用商店应用程序也需要新的收集技术。 请参阅 [Windows 8 和 Windows Server 2012 应用程序上的性能工具](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)。  
  
## <a name="common-tasks"></a>常规任务  
  
|任务|相关内容|  
|----------|---------------------|  
|**附加到正在运行的 .NET 服务**|-   [如何：将探查器附加到 .NET 服务以收集并发数据](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**添加层交互数据**|-   [收集层交互数据](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**附加到正在运行的 C/C++ 服务**|-   [如何：将探查器附加到本机服务以收集并发数据](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>相关任务  
  
### <a name="profiling-windows-services"></a>分析 Windows 服务  
  
|任务|相关内容|  
|----------|---------------------|  
|**使用采样方法进行分析**|-   [使用采样法收集应用程序统计信息](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**使用检测方法进行分析**|-   [使用检测收集详细计时数据](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**分析 .NET 内存分配和垃圾回收**|-   [收集 .NET 内存数据](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="profiling-concurrency-data"></a>分析并发数据  
  
|任务|相关内容|  
|----------|---------------------|  
|**分析独立应用程序**|-   [收集并发数据](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**分析 ASP.NET Web 应用程序**|-   [收集并发数据](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### <a name="analyzing-concurrency-data-views-and-reports"></a>分析并发数据视图和报告  
 [资源争用数据视图](../profiling/resource-contention-data-views.md)  
  
 [并发可视化工具](../profiling/concurrency-visualizer.md)  
  
## <a name="reference"></a>参考  
 [命令行分析工具参考](../profiling/command-line-profiling-tools-reference.md)



