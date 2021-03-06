---
title: 收集其他性能数据 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 562f1cf090ffe169ead30b3bd7c4bdce515d3b22
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
ms.locfileid: "34266321"
---
# <a name="collect-additional-performance-data"></a>收集其他性能数据

除使用分析方法收集的数据外，Visual Studio 分析工具还使你能够记录和查看其他数据。

## <a name="common-tasks"></a>常见任务

|任务|相关的内容|
|----------|---------------------|
|**收集应用程序中 ADO.NET 调用的性能数据。** 添加有关应用程序对数据库执行的同步调用的数据。|- [收集层交互数据](../profiling/collecting-tier-interaction-data.md)|
|**收集 Windows 性能计数器数据。** 将系统性能计数器作为分析标记添加到分析数据中。 标记可用于筛选报表。|- [如何：收集 Windows 计数器数据](../profiling/how-to-collect-windows-counter-data.md)|
|**收集 Windows 事件跟踪数据。** 收集 Windows 事件跟踪 (ETW) 数据，从而记录应用程序和系统事件，但不记录分析数据。|- [如何：收集 Windows 事件跟踪 (ETW) 数据](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|