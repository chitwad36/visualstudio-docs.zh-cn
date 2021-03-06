---
title: 在 Visual Studio 中创建解决方案和项目
ms.date: 02/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.openprojectfromweb
- vs.newproject
- VS.ToolsOptionsPages.Projects.General
- SolutionItemsProject
helpviewer_keywords:
- solutions [Visual Studio], creating
- projects [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6d8d222a35c06cd7d53e2e104761cc1f30bf816e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49813812"
---
# <a name="create-solutions-and-projects"></a>创建解决方案和项目

*项目*是 Visual Studio 中的逻辑容器，用于存放生成应用所需的项，比如源代码文件、位图、图标以及组件和服务引用。 创建新项目时，Visual Studio 会创建一个解决方案来包含该项目。 然后可以根据需要向解决方案添加其他新项目或现有项目。 解决方案还可以包含未连接到任何特定项目的文件。

![解决方案/项目层次结构](./media/vside-proj-soln.png)

可在名为“解决方案资源管理器”的工具窗口中查看解决方案和项目。 以下屏幕截图显示“解决方案资源管理器”中的一个示例解决方案 (BikeSharing.Xamarin-UWP)，该解决方案 包含两个项目：BikeSharing.Clients.Core 和 BikeSharing.Clients.Windows。 每个项目均包含多个文件、文件夹和引用。 粗体形式的项目名称是*启动项目*；即，运行应用时启动的项目。 可以指定将哪个项目作为启动项目。

![包含项目的解决方案资源管理器](./media/vside-solution-explorer-projects.png)

用户可以通过向项目添加必要文件来自行构造项目，与此同时，Visual Studio 也提供了一组精选的项目模板，让用户能够拥有一个好的开端。 从模板新建的项目将具有该项目类型的必需元素，用户可在必要时重命名文件，或向项目添加新代码或现有代码以及其他资源。

也就是说，在 Visual Studio 中开发应用时不需要解决方案和项目。 用户也可以直接打开从 Git 克隆或从其他地方下载的代码。 有关详细信息，请参阅[在 Visual Studio 中开发代码而无需创建项目或解决方案](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)。

> [!NOTE]
> 本主题中的说明基于 Visual Studio Community 版。 您看到的对话框和菜单命令可能与此处描述的有所不同，这取决于您的设置或 Visual Studio 版本。 若要更改设置，例如“常规”或“Visual C++”设置，请选择“工具”，“导入和导出设置”，然后选择“重置所有设置”。

## <a name="to-create-a-project-from-a-project-template"></a>从项目模板创建项目

1. 可通过多种方式在 Visual Studio 中创建新项目。 在起始页上，在“搜索项目模板”框中输入项目模板的名称，或选择“创建新项目”链接打开“新建项目”对话框。 也可以选择菜单栏上的“文件” > “新建” > “项目”，或选择工具栏上的“新建项目”按钮。

   ![起始页](./media/vside-newproject1.png)

   在“新建项目”对话框中的“模板”类别下，可用项目模板以列表形式列出。 模板按编程语言和项目类型（如 Visual C#、JavaScript 和 Azure Data Lake）归类。

   ![“新建项目”对话框](./media/vside-newproject-templates-list.png)

   > [!NOTE]
   > 显示的可用语言和项目模板列表取决于正在运行的 Visual Studio 版本和安装的工作负载。 若要了解如何安装附加工作负载，请参阅[通过添加或删除工作负载和组件修改 Visual Studio 2017](../install/modify-visual-studio.md)。

2. 通过选择语言名称旁边的三角形，然后选择项目类型，可显示要使用的编程语言的模板列表。

   以下示例演示可用于 Visual C# .NET Core 项目的项目模板。

   ![项目模板](./media/new-project-dialog-net-core.png)

3. 在“名称”框中输入新项目的名称。 可选择将项目保存在系统上的默认位置，或选择“浏览”按钮查找其他位置。

   还可以选择更改解决方案名称，或选择“添加到源代码管理”以将新项目添加到 Git 存储库。

4. 选择“确定”按钮，创建解决方案和项目。

5. 如果要向解决方案添加附加项目，请在“解决方案资源管理器”中选择解决方案节点，然后在菜单栏上选择“项目” > “添加新项”。

## <a name="create-a-project-from-existing-code-files"></a>从现有代码文件创建项目

如果有一组代码源文件，可以轻松地将它们添加到项目。

1. 在菜单上，依次选择“文件” > “新建” > “从现有代码创建项目”。

1. 在“从现有代码文件创建项目”向导的“要创建什么类型的项目?”下拉列表框中，选择所需的项目类型，然后选择“下一步”按钮。

1. 在向导中，浏览到文件位置，然后在“名称”框中输入新项目的名称。 完成后，选择“完成”按钮。

> [!NOTE]
> 此选项最适合相对简单的文件集合。 目前仅支持 Visual C++、Apache Cordova、Visual Basic 和 C# 项目类型。

## <a name="add-files-to-a-solution"></a>将文件添加到解决方案

如果有一个适用于多个项目的文件，比如解决方案的自述文件，或其他逻辑上属于解决方案级别而不是位于特定项目下的文件，则可以将它们添加到解决方案自身。 若要将某项添加到解决方案，请在“解决方案资源管理器”中解决方案节点的上下文（右击）菜单上，依次选择“添加” > “新项”，或依次选择“添加” > “现有项”。

## <a name="create-a-net-project-that-targets-a-specific-version-of-the-net-framework"></a>创建面向 .NET Framework 特定版本的 .NET 项目

创建项目时，可指定想要项目使用的特定 .NET Framework 版本。 若要指定 .NET Framework 版本，请选择“新建项目”对话框中的“Framework”下拉菜单。

![“新建项目”对话框中的“框架”下拉列表](./media/vside-newproject-framework.png)

> [!NOTE]
> 必须在系统上安装 .NET Framework 3.5 才能访问 .NET Framework 4 以前的 .NET Framework 版本。

## <a name="create-empty-solutions"></a>创建空的解决方案

还可以创建不包含任何项目的空解决方案。 这可能更适合想从头开始构造解决方案和项目的情况。

### <a name="to-create-an-empty-solution"></a>创建空解决方案

1. 在菜单上，依次选择“文件” > “新建” > “项目”。

1. 在左侧（“模板”）窗格中，依次选择展开列表中的“其他项目类型” > “Visual Studio 解决方案”。

1. 在中间窗格中，选择“空白解决方案”。

1. 输入解决方案的“名称”和“位置”值，然后选择“确定”。

创建空白解决方案后，可以选择“项目”菜单上的“添加新项”或“添加现有项”，将新的或现有的项目或项添加到解决方案中。

如前文所述，还可以打开代码文件而无需创建项目或解决方案。 若要了解如何按照此方法开发代码，请参阅[在 Visual Studio 中开发代码而无需创建项目或解决方案](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)。

## <a name="create-a-temporary-project-c-and-visual-basic"></a>创建临时项目（C# 和 Visual Basic）

如果创建基于 .NET 的项目时不指定磁盘位置，它就是一个临时项目。 临时项目可用于试验 .NET 项目。 使用临时项目时，可以随时选择保存或放弃它。

若要创建临时项目，请先转到“工具” > “选项” > “项目和解决方案” > “常规”，取消选中“创建时保存新项目”复选框。 然后照常打开“新建项目”对话框。

## <a name="delete-a-solution-project-or-item"></a>删除解决方案、项目或项

可以永久删除解决方案及其内容，但不能通过 Visual Studio IDE 执行。 在 Visual Studio 中删除项只会将它们从当前解决方案或项目中移除。 若要从系统中永久删除解决方案或其他组件，请使用文件资源管理器删除包含 .sln 和 .suo 解决方案文件的文件夹。 但是，在永久删除解决方案之前，建议备份好所有项目或文件，以防再次需要它们。

> [!NOTE]
> .suo 文件是隐藏文件，在默认的文件资源管理器设置下不会显示。 若要显示隐藏文件，请在文件资源管理器的“查看”菜单上选中“隐藏项”复选框。

### <a name="to-permanently-delete-a-solution"></a>永久删除解决方案

1. 在“解决方案资源管理器”中，在要删除的解决方案的上下文菜单上选择“在文件资源管理器中打开文件夹”。

1. 在文件资源管理器中，导航到上一级。

1. 选择包含解决方案的文件夹，然后选择 Delete 键。

## <a name="see-also"></a>请参阅

- [解决方案和项目](../ide/solutions-and-projects-in-visual-studio.md)
- [GitHub 上的 Microsoft 开放源代码存储库](https://github.com/Microsoft)
- [开发者代码示例](https://code.msdn.microsoft.com/)