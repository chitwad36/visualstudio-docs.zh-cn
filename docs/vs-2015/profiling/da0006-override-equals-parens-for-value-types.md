---
title: DA0006：替代值类型的 Equals() | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.rules.DAOverrideEquals
- vs.performance.6
- vs.performance.DA0006
- vs.performance.rules.DA0006
ms.assetid: 4d85bdd6-b571-47e0-afd6-ba3764e4eed5
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2e09783d5961172033a82e8be8285d9398992ef
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49285407"
---
# <a name="da0006-override-equals-for-value-types"></a>DA0006：重写值类型的 Equals()
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

规则 Id |DA0006 |  
|类别 |。NET Framework 使用情况 |  
|分析方法 |采样 |  
|消息 |重写 Equals 和相等运算符的值类型。 |  
|消息类型 |警告 |  
  
## <a name="cause"></a>原因  
 对 Equals 方法或公共值类型的相等运算符的调用在分析数据中占很大比例。 请考虑实施更有效的方法。  
  
## <a name="rule-description"></a>规则说明  
 对于值类型，Equals 的继承的实现使用 <xref:System.Reflection> 库，并比较类型中所有字段的内容。 反射需要消耗大量计算资源，可能没有必要比较每一个字段是否相等。 如果希望用户对实例进行比较或排序，或者希望用户将它们用作哈希表键，则值类型应实现 Equals。 如果编程语言支持运算符重载，则还应提供相等和不等运算符的实现。  
  
 有关如何重写 Equals 和相等运算符的详细信息，请参阅 [Equals 和相等运算符 (==) 的实现准则](http://go.microsoft.com/fwlink/?LinkId=177818)。  
  
## <a name="how-to-investigate-a-warning"></a>如何调查警告  
 有关实现 Equals 和相等运算符的示例，请参阅代码分析规则 [CA1815：替代值类型上的 Equals 和相等运算符](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)



