---
title: 引用元素 （Visual Studio 模板） |Microsoft Docs
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
- http://schemas.microsoft.com/developer/vstemplate/2005#Reference
helpviewer_keywords:
- Reference element [Visual Studio templates]
- <Reference> element [Visual Studio templates]
ms.assetid: 852772ea-c324-42e9-8c8a-6d565414a109
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 15de6b3ef890735a83c4ca5ac84a54a71f5c247a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49303922"
---
# <a name="reference-element-visual-studio-templates"></a>Reference 元素（Visual Studio 模板）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

指定向项目添加项时要添加的程序集引用。  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<引用 >  
 \<引用 >  
  
## <a name="syntax"></a>语法  
  
```  
<Reference>  
    <Assembly> ... </Assembly>  
</Reference>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下各部分描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[Assembly](../extensibility/assembly-element-visual-studio-templates.md)|必需的元素。<br /><br /> 指定有关程序集，该模板使用以将该程序集的引用添加到项目的信息。 必须有一个`Assembly`元素中的每个`Reference`元素。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[参考资料](../extensibility/references-element-visual-studio-templates.md)|该模板将添加到项目的程序集引用进行分组。|  
  
## <a name="remarks"></a>备注  
 `Reference` 是 `References` 的必需子元素。  
  
 `Reference`并`References`仅具有的.vstemplate 文件中使用元素`Type`属性的值`Item`。  
  
## <a name="example"></a>示例  
 下面的示例演示`TemplateContent`项模板的元素。 此 XML 将添加对 System.dll 和 System.Data.dll 程序集的引用。  
  
```  
<TemplateContent>  
    <References>  
        <Reference>  
            <Assembly>  
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>  
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
    </References>  
    ...  
</TemplateContent>  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)

