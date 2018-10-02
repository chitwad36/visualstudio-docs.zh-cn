---
title: CA1005： 避免泛型类型参数过多 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d807fc581b6c4f0c06b2b2de1c86a148c30c4ff7
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587490"
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005：避免泛型类型的参数过多
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA1005： 避免泛型类型参数过多](https://docs.microsoft.com/visualstudio/code-quality/ca1005-avoid-excessive-parameters-on-generic-types)。

|||
|-|-|
|TypeName|AvoidExcessiveParametersOnGenericTypes|
|CheckId|CA1005|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 外部可见的泛型类型具有两个以上的类型参数。

## <a name="rule-description"></a>规则说明
 泛型类型包含的类型参数越多，越难以知道并记住每个类型参数各代表什么。 它是使用一个类型参数，如下所示通常明显`List<T>`，并在某些情况下，使用两个类型参数，如下所示`Dictionary<TKey, TValue>`。 如果两个以上的类型参数已存在，都会感到过于困难对于大多数用户 (例如， `TooManyTypeParameters<T, K, V>` C# 中或`TooManyTypeParameters(Of T, K, V)`中[!INCLUDE[vbprvb](../includes/vbprvb-md.md)])。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请更改设计以使用不超过两个类型参数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 除非设计确实需要两个以上的类型参数，否则不要禁止显示此规则的警告。 提供易于理解和使用的语法中的泛型可减少所需了解和提高新库的使用率的时间。

## <a name="related-rules"></a>相关的规则
 [CA1010：集合应实现泛型接口](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000：不要在泛型类型中声明静态成员](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002：不要公开泛型列表](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006：不要将泛型类型嵌套在成员签名中](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004：泛型方法应提供类型形参](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003：使用泛型事件处理程序实例](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007：在适用处使用泛型](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>请参阅
 [泛型](http://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)


