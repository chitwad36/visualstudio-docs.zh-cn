---
title: 如何： 将依赖项添加到 VSIX 包 |Microsoft Docs
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
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ebd835fef9df8fbdeb67bdf9c7e6eff31bcf4730
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481395"
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>如何： 将依赖项添加到 VSIX 包
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 将依赖项添加到 VSIX 包](https://docs.microsoft.com/visualstudio/extensibility/how-to-add-a-dependency-to-a-vsix-package)。  
  
您可以设置安装尚不存在于目标计算机上的任何依赖项的 VSIX 包部署。 若要实现此目的，包括到 source.extension.vsixmanifest 文件中的 VSIX 依赖项。  
  
#### <a name="to-add-a-dependency"></a>若要添加的依赖项  
  
1.  打开 source.extension.vsixmanifest 文件中的**设计**视图。 转到**依赖项**选项卡，单击**新建**。  
  
2.  若要添加的已安装的扩展： 在**添加新依赖关系**对话框中，选择**已安装扩展**，然后针对**名称**，选择列表中的扩展。  
  
3.  若要添加另一个未安装的 VSIX:: 中**添加新依赖关系**对话框中，选择**在文件系统上的文件**，然后使用**浏览**按钮以选择 VSIX。  
  
## <a name="see-also"></a>请参阅  
 [VSIX 扩展架构 1.0 参考](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [VSIX 包的剖析](../extensibility/anatomy-of-a-vsix-package.md)   
 [准备 Windows Installer 部署的扩展](../extensibility/preparing-extensions-for-windows-installer-deployment.md)
