---
title: CreatePkgDef 实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- package definition
- create pkgdef
- pkgdef
- createpkgdef
ms.assetid: c745cb76-47a6-49ff-9eed-16af0f748e35
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 63334ba9d454407bb93a87bf89b12cb472184d58
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49181592"
---
# <a name="createpkgdef-utility"></a>CreatePkgDef 实用工具
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

采用 Visual Studio 扩展中作为参数的.dll 文件并创建伴随该.dll 的.pkgdef 文件。 .Pkgdef 文件包含否则会在安装该扩展时写入到系统注册表的所有信息。  
  
> [!NOTE]
>  大部分自动包含在 Visual Studio SDK 中的项目模板创建.pkgdef 文件作为生成过程的一部分。 本文档旨在为那些想要手动创建包或转换现有的包以使用.pkgdef 部署。  
  
## <a name="syntax"></a>语法  
  
```  
CreatePkgDef /out=FileName [/codebase] [/assembly] AssemblyPath  
```  
  
## <a name="arguments"></a>自变量  
 / out =`FileName`  
 必须的。 设置到.pkgdef 输出文件的名称`FileName`。  
  
 /codebase  
 可选。 强制注册到的基本代码实用程序。  
  
 /assembly  
 强制使用程序集实用程序的注册。  
  
 `AssemblyPath`  
 你想要生成.pkgdef 的.dll 文件的路径。  
  
## <a name="remarks"></a>备注  
 通过使用.pkgdef 文件的扩展部署将替换 Visual Studio 的早期版本的注册表要求。  
  
 .Pkgdef 文件必须安装在以下位置之一： %localappdata%\Microsoft\Visual Studio\14.0\Extensions\ 或 %vsinstalldir%\Common7\IDE\Extensions\\。 如果安装文件夹是 %localappdata%\Microsoft\Visual Studio\14.0\Extensions\\，扩展将识别的 Visual Studio 中，但默认情况下将禁用。 用户可以启用扩展，通过使用**扩展和更新**。 如果安装文件夹是 %vsinstalldir%\Common7\IDE\Extensions\\，默认情况下启用扩展。  
  
> [!NOTE]
>  **扩展和更新**工具不能用于访问扩展，除非它作为 VSIX 包的一部分安装。  
  
## <a name="see-also"></a>请参阅  
 [CreateExpInstance 实用工具](../../extensibility/internals/createexpinstance-utility.md)

