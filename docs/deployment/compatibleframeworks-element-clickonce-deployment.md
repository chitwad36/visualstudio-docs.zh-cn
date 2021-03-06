---
title: '&lt;compatibleFrameworks&gt;元素 （ClickOnce 部署） |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <compatibleFrameworks> element [ClickOnce deployment manifest]
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44329fc4c2ec5e9f2f8352d69ea487f23cbe3c5a
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077680"
---
# <a name="ltcompatibleframeworksgt-element-clickonce-deployment"></a>&lt;compatibleFrameworks&gt;元素 （ClickOnce 部署）
标识此应用程序可在其上安装和运行的 .NET Framework 版本。  
  
> [!NOTE]
>  [*MageUI.exe* ](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)不支持`compatibleFrameworks`元素时保存应用程序清单已签名证书使用[ *MageUI.exe*](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)。 相反，必须使用[ *Mage.exe*](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)。  
  
## <a name="syntax"></a>语法  
  
```xml  
<compatibleFrameworks  
      SupportUrl>   
   <framework  
      targetVersion  
      profile  
      supportedRuntime  
   />   
</ compatibleFrameworks>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `compatibleFrameworks`元素是必需的部署清单面向[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]运行时提供的[!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)]或更高版本。 `compatibleFrameworks`元素包含一个或多个`framework`元素，用于指定此应用程序可以在其运行的.NET Framework 版本。 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]运行时将运行该应用程序在第一个可用`framework`此列表中。  
  
 下表列出了该属性的`compatibleFrameworks`元素支持。  
  
|特性|描述|  
|---------------|-----------------|  
|`S` `upportUrl`|可选。 指定首选的兼容.NET Framework 版本，可以下载的 URL。|  
  
## <a name="framework"></a>框架  
 必须的。 下表列出了属性的`framework`元素支持。  
  
|特性|描述|  
|---------------|-----------------|  
|`targetVersion`|必须的。 指定的目标.NET Framework 的版本号。|  
|`profile`|必须的。 指定目标.NET Framework 的配置文件。|  
|`supportedRuntime`|必须的。 指定的目标.NET Framework 与相关联的运行时的版本号。|  
  
## <a name="remarks"></a>备注  
  
## <a name="example"></a>示例  
 下面的代码示例演示`compatibleFrameworks`中的元素[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]部署清单。 可以在上运行此部署[!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]。 它还可以运行[!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)]因为它是一个超集[!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]。  
  
```xml  
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
  <framework   
      targetVersion="4.0"   
      profile="Client"   
      supportedRuntime="4.0.30319" />  
</compatibleFrameworks>  
```  
  
## <a name="see-also"></a>请参阅  
 [ClickOnce 部署清单](../deployment/clickonce-deployment-manifest.md)