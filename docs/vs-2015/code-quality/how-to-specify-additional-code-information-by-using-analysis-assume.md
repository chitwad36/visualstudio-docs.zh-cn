---
title: 如何： 使用 __analysis_assume 指定其他代码信息 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- __analysis_assume
helpviewer_keywords:
- __analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
caps.latest.revision: 12
author: corob-msft
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 608ae6383f95122d5e4b85658b12d454dec24d4e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49202535"
---
# <a name="how-to-specify-additional-code-information-by-using-analysisassume"></a>如何：使用 __analysis_assume 指定其他代码信息
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

您可以对代码分析工具的提示，它们将帮助分析过程并降低警告 C/c + + 代码。 若要提供的其他信息，请使用以下函数：  
  
 `__analysis_assume(`  `expr`  `)`  
  
 `expr` -假定为计算结果为 true 的任何表达式。  
  
 代码分析工具假设由表达式表示的条件是在其中该函数将显示，并将保持为 true，直到表达式更改，例如，通过对变量赋值的点，则返回 true。  
  
> [!NOTE]
>  `__analysis_assume` 不会影响代码优化。 外部代码分析工具，`__analysis_assume`定义为执行任何操作。  
  
## <a name="example"></a>示例  
 下面的代码使用`__analysis_assume`若要更正代码分析警告[C6388](../code-quality/c6388.md):  
  
```  
#include<windows.h>  
#include<codeanalysis\sourceannotations.h>  
  
using namespace vc_attributes;  
  
// calls free and sets ch to null  
void FreeAndNull(char* ch);  
  
//requires pc to be null  
void f([Pre(Null=Yes)] char* pc);  
  
void test( )  
{  
  char *pc = (char*)malloc(5);  
  FreeAndNull(pc);  
  __analysis_assume(pc == NULL);   
  f(pc);  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [__assume](http://msdn.microsoft.com/library/d8565123-b132-44b1-8235-5a8c8bff85a7)



