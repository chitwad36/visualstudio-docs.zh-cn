---
title: 用于本地化的资源的分层组织
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- resource files, localized
- localization [Visual Studio], resources
- fallback resources
- international applications [Visual Studio], storing resources
- satellite assemblies, resource hierarchies
- globalization [Visual Studio], resources
- satellite assemblies
- resources [Visual Studio], fallback system
- resource files, fallback processes
ms.assetid: dadf8f2c-f74c-44d7-bec0-a1e956d8d38d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f21b4c6d53a70cb3d695c05e412b0e2f52a607bb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49874556"
---
# <a name="hierarchical-organization-of-resources-for-localization"></a>用于本地化的资源的分层组织

在 Visual Studio 中，本地化资源（适用于各区域性的字符串和图像等数据）存储在单独的文件中并根据 UI 区域性设置进行加载。 若要了解本地化资源是如何加载的，可以将其想象成按层次结构的方式进行组织。

## <a name="kinds-of-resources-in-the-hierarchy"></a>层次结构中的资源种类

- 默认区域性的回退资源（例如英语 ("en")）位于层次结构的顶部。 这些回退资源是唯一不具有自有文件的资源；它们存储在主程序集中。

- 回退资源下方是任何非特定区域性的资源。 非特定区域性与一种语言而非国家/地区相关联。 例如，法语 ("fr") 是一个非特定区域性。 （回退资源也用于非特定区域性，但用于特殊的非特定区域性。）

- 非特定区域性资源下方是任何特定区域性的资源。 特定区域性与一种语言而非国家/地区相关联。 例如，加拿大法语 ("fr-CA") 是一个特定区域性。

如果一个应用程序尝试加载任何本地化资源，例如一个字符串，且未找到它，则会搜索整个层次结构，直到找到包含所请求的资源的资源文件为止。

存储资源的最佳方式是尽可能将资源一般化。 也就是说，尽可能将本地化的字符串、图像等存储在非特定区域性的资源文件中，而不是特定区域性的资源文件中。 例如，如果你具有比利时法语 ("fr-BE") 区域性的资源以及紧邻英语回退资源且位于其上方的资源，那么如果某人使用一个系统上的应用程序且该系统配置为加拿大法语区域性，则可能会发生问题。 该系统查找“fr-CA”的附属程序集，但找不到它，因而加载包含英语回退资源的主程序集，而不是加载法语资源。 下图显示了存在这种问题的情况。

![仅特定资源](../ide/media/vbspecificresourcesonly.gif)

如果遵循上述建议的做法，即将尽可能多的资源放置在“fr”区域性的非特定区域性资源文件中，则加拿大法语用户不会看到为“fr-BE”区域性所标记的资源，而是会看到法语字符串。 下面的情况显示了这一建议使用的方案。

![NeutralSpecificResources 图](../ide/media/vbneutralspecificresources.gif)

## <a name="see-also"></a>请参阅

- [用于本地化的非特定资源语言](../ide/neutral-resources-languages-for-localization.md)
- [安全性和已本地化的附属程序集](../ide/security-and-localized-satellite-assemblies.md)
- [实现应用程序本地化](../ide/localizing-applications.md)
- [对应用程序进行全球化和本地化](../ide/globalizing-and-localizing-applications.md)