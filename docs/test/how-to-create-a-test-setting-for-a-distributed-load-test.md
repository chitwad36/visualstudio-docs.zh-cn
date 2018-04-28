---
title: 在 Visual Studio 中为分布式负载测试创建测试设置
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- test settings, for distributed load tests
ms.assetid: b63d4b71-3b74-4872-b2d1-f0bd1a9a8544
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 1b9ffd7206023885fc45e66af585ca34f75ce67f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-test-setting-for-a-distributed-load-test"></a>如何：为分布式负载测试创建测试设置

配置负载测试的“测试设置”，以便可以使用测试代理和测试控制器在多台计算机间分发这些测试。 还可以将测试设置配置为使用诊断数据适配器，这些适配器指定从 Visual Studio 中运行负载测试时要收集的数据类型或者对测试计算机产生的影响。

例如，可以使用 ASP.NET 探查器诊断数据适配器来收集代码的性能明细。 此外，诊断数据适配器可用于在测试计算机上模拟潜在瓶颈或减少可用系统内存。

Visual Studio 的测试设置存储在一个文件中。 测试设置定义了有关每个角色的以下信息：

-   受测应用程序所需的角色集

-   运行测试所使用的角色

-   用于每个角色的诊断数据适配器

运行测试时，你根据对该特定测试运行的要求，选择要用作活动测试设置的测试设置。 测试设置文件存储为解决方案的一部分。 该文件名的扩展名为 .testsettings。

将 Web 性能和负载测试项目添加到解决方案中时，将创建一个 Default.testsettings 文件。 该文件将自动添加到“解决方案项”文件夹下的解决方案中。 该文件在本地运行测试，无需任何诊断数据适配器。 可添加另一个 .testsettings 文件或编辑 .testsettings 文件以指定诊断数据适配器和测试控制器。

测试控制器将拥有可用于测试设置中的每个角色的代理。 有关测试控制器和测试代理的详细信息，请参阅[使用 Visual Studio 管理测试控制器和测试代理](../test/manage-test-controllers-and-test-agents.md)。

按照以下这些步骤可在解决方案中为计划从 Visual Studio 中运行的负载测试创建和移除测试设置。

## <a name="create-a-test-setting-for-a-distributed-load-test"></a>为分发的负载测试创建测试设置

### <a name="to-add-a-test-settings-for-a-distributed-load-test"></a>为分布式负载测试添加测试设置

1.  在“解决方案资源管理器”中，右键单击“解决方案项”，指向“添加”，然后选择“新建项”。

     “添加新项”对话框随即出现。

2.  在“已安装的模板”窗格中，选择“测试设置”。

3.  （可选）在“名称”框中更改测试设置文件的名称。

4.  选择“添加”。

     新的测试设置文件将出现在“解决方案资源管理器”中的“解决方案项”文件夹下。

    > [!NOTE]
    > Visual Studio Enterprise 所显示的测试设置列表派生自“解决方案项”文件夹中的测试设置文件列表。 例如，在使用“测试”菜单上的“选择活动的测试设置”选项时，将显示“解决方案项”文件夹中的测试设置文件。 这表明，如果将测试设置文件移动到解决方案层次结构中的其他位置，那么该文件不能再用作 Visual Studio 集成开发环境中的测试设置。

5.  此时会显示“测试设置”对话框。 “常规”页处于选中状态。

     你现在可以编辑并保存测试设置值。

    > [!NOTE]
    > 将列出创建的每个测试设置，作为“测试”菜单上“选择活动的测试设置”和“编辑测试设置”选项的选择。

6.  在“名称”下键入测试设置的名称。

7.  （可选）在“说明”下，键入测试设置的说明，以便其他团队成员了解其用途。

8.  （可选）若要选择测试运行的默认命名方案，请选择“默认命名方案”。 若要定义自己的命名方案，请选择“用户定义的方案”，然后在“前缀文本”中键入所需的文本。 若要将日期和时间戳追加到测试运行名称，请选择“追加日期时间戳”。

9. 选择“角色”。

     此时将显示“角色”页。

     ![测试设置角色](../test/media/load_testtestrole.png "Load_TestTestRole")

10. 若要远程运行测试，或者远程运行测试并远程收集数据，请使用“测试执行方法”下拉列表并选择“远程执行”。

11. 使用“控制器”下拉列表从“控制器”中为测试代理选择将用于运行测试或收集数据的测试控制器。

    > [!NOTE]
    > 如果这是首次添加控制器，则下拉列表中不会列出任何控制器。 列表由先前在其他测试设置中指定的控制器填充。 必须在框中键入控制器的名称（例如，TestControllerMachine1）。

12. 若要添加要用于运行测试和收集数据的角色，请在“角色”下选择“添加”。

13. 在“名称”列中键入角色的名称。 例如，角色可以是“Web 服务器”。

14. 重复步骤 12 和 13，添加所需的所有角色。

     每个角色都使用由测试控制器管理的测试代理。

15. 选择要运行测试的角色，然后选择“设置为运行测试的角色”。

    > [!IMPORTANT]
    > 创建和定义的其他角色不运行测试，仅用于根据在“数据和诊断”页中为角色指定的数据和诊断适配器收集数据。

16. 若要限制可用于角色的代理，请选择角色，然后在“所选角色的代理特性”下方的工具栏中选择“添加”。

     此时将显示“代理选择规则”对话框。

     在“特性名”中键入名称，在“特性值”中键入值，然后选择“确定”。 根据需要添加多个特性。

     例如，可以添加一个名为“RAM > 16GB”并且值为“True”或“False”的特性，以对内存大于 16GB 的测试代理计算机进行筛选。 若要将同一特性应用于一个或多个测试代理，请使用“管理测试控制器”对话框。 有关详细信息，请参阅[使用 Visual Studio 管理测试控制器和测试代理](../test/manage-test-controllers-and-test-agents.md)。

17. 选择“数据和诊断”。

     此时将显示“数据和诊断”页。

     ![测试设置数据和诊断](../test/media/load_testtest.png "Load_TestTest")

18. 在“数据和诊断”页中，通过选择角色将用于收集数据的“诊断数据适配器”来定义角色所起的作用。 因此，如果对角色启用了一个或多个数据和诊断适配器，则测试控制器将基于为角色定义的特性选择一个可用的测试代理计算机来为指定的数据和诊断适配器收集数据。 若要选择要为每个角色收集的数据和诊断数据适配器，请选择角色。 根据测试要求为每个角色选择诊断数据适配器。 若要配置为每个角色选择的每个诊断数据适配器，请选择“配置”。

     **角色和诊断数据适配器示例：**

     例如，可以创建一个名为“桌面客户端”且“使用 SQL”特性设置为“True”的客户端角色，以及一个名为“SQL Server”且特性设置为“RAM > 16GB”的服务器角色。 如果通过在“角色”页中选择“设置为运行测试的角色”指定“桌面客户端”将运行测试，则测试控制器将选择包含“使用 SQL”属性设置为“True”的测试代理的计算机来运行测试。 测试控制器还将选择具有包含“RAM > 16GB”特性的测试代理的 SQL Server 计算机（仅用于收集角色中包含的数据和诊断适配器定义的数据）。 如果也为“桌面客户端”角色选择了数据和诊断适配器，则“桌面客户端”测试代理还可以为它在其上运行的计算机收集数据。

     有关每个诊断数据适配器及其配置方法的详细信息，可查看下表中的关联主题。

     有关诊断数据适配器的详细信息，请参阅[使用测试设置收集诊断信息](../test/collect-diagnostic-information-using-test-settings.md)。

     **用于负载测试的诊断数据适配器**

    |诊断数据适配器|在负载测试中使用|关联主题|
    |-----------------------------|-------------------------|----------------------|
    |**用于 IntelliTrace 和测试影响的 ASP.NET 客户端代理：**此代理允许你为 IntelliTrace 和测试影响诊断数据适配器收集有关从客户端到 Web 服务器的 http 调用的信息。|![“信息”图标](../test/media/vc364f4.gif)<br /><br /> 除非你具有收集测试代理计算机的系统信息的特定需要，否则不要包含此适配器。 注意：建议不要在负载测试中使用 IntelliTrace 适配器，因为这样会因收集的数据量太大而导致问题。 <br /><br /> 测试影响数据不是使用负载测试收集到的。||
    |**IntelliTrace：**可以配置特定诊断跟踪信息，该信息存储在一个日志文件中。 该日志文件的扩展名为 .tdlog。 运行测试时如果某个测试步骤未通过，则可以创建一个 Bug。 包含诊断跟踪的日志文件会自动附加到此 Bug 中。 该日志文件中收集的数据可减少重现和诊断代码中的错误所需的时间，从而提高调试效率。 可以基于此日志文件在另一台计算机上重新创建本地会话。 这会降低无法重现 Bug 的风险。<br /><br /> 有关详细信息，请参阅[收集 IntelliTrace 数据](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md)。|![“重要事项”图标](../test/media/vc364f3.gif)<br /><br /> 我们建议不要在负载测试中使用 IntelliTrace 适配器，因为这样会因收集和记录的数据量太大而导致问题。 应该仅在运行时间不长、使用的测试代理不多的负载测试中尝试使用 IntelliTrace 适配器。|[如何：收集 IntelliTrace 数据以帮助调试难题](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md)|
    |**ASP.NET 探查器：**可以创建包含 ASP.NET 分析的测试设置，该分析收集 ASP.NET Web 应用程序的性能数据。|ASP.NET 探查器诊断数据适配器分析 Internet Information Services (IIS) 进程，因此它不针对开发 Web 服务器工作。 若要在负载测试中分析网站，必须在运行 IIS 的计算机上安装测试代理。 测试代理不生成负载，它是仅用于收集的代理。 有关详细信息，请参阅[安装和配置测试代理](../test/lab-management/install-configure-test-agents.md)。|[如何：使用测试设置为负载测试配置 ASP.NET 探查器](../test/how-to-configure-aspnet-profiler-for-load-tests-using-test-settings.md)|
    |**事件日志**：可以将测试设置配置为包含事件日志收集，该事件日志将包含在测试结果中。||[如何：使用测试设置配置事件日志收集](http://msdn.microsoft.com/en-us/48d67891-6018-4549-83e3-213d5d824a02)|
    |**网络仿真：**可以使用测试设置指定希望在测试中放置人工网络负载。 网络仿真将仿真特定网络连接（如拨号连接）的速度，从而影响计算机的往来通信。 注意：网络仿真不能用于提高网络连接速度。|负载测试会忽略网络仿真适配器。 实际上，负载测试使用在负载测试方案的网络组合中指定的设置。<br /><br /> 有关详细信息，请参阅[指定虚拟网络类型](../test/specify-virtual-network-types-in-a-load-test-scenario.md)。||
    |**系统信息：**可以设置测试设置来包含有关在其上运行系统信息诊断和数据收集器的计算机的系统信息。 通过使用测试设置可在测试结果中指定系统信息。|![“信息”图标](../test/media/vc364f4.gif)<br /><br /> 你可以从负载代理和测试中的系统收集系统信息。|收集此信息不需要任何配置。|
    |**测试影响：**可以收集在运行某个测试用例时使用了哪些应用程序代码方法的相关信息。 将它与开发人员进行的应用程序代码更改结合使用，可确定这些开发更改影响了哪些测试。|测试影响数据不是使用负载测试收集到的。||
    |**视频录制器：**运行自动测试时可以创建桌面会话的视频记录。 这对查看编码的 UI 测试的用户操作非常有用。 该视频可帮助其他团队成员隔离难以重现的应用程序问题。 注意：远程运行测试时，除非代理在交互式进程模式下运行，否则视频录制器不起作用。|![“重要事项”图标](../test/media/vc364f3.gif)注意：建议不要对负载测试使用视频录制器适配器。|[如何：使用测试设置在测试期间包括屏幕和语音录制](../test/how-to-include-recordings-of-the-screen-and-voice-during-tests.md)|

19. 选择“部署”。

     此时将显示“部署”页。

20. 若要在每次运行测试时都为部署创建一个单独的目录，请选择“启用部署”。

    > [!NOTE]
    > 如果这样做，则在运行测试时可以继续生成应用程序。

21. 若要将文件添加到用于运行测试的目录，请选择“添加文件”，然后选择要添加的文件。

    > [!NOTE]
    > 运行负载测试时，插件程序集、数据文件和上载的文件将自动部署。

22. 若要将目录添加到用于运行测试的目录，请选择“添加目录”，然后选择要添加的目录。

23. 若要在测试前后运行脚本，请选择“安装脚本和清理脚本”。

     此时将显示“安装脚本和清理脚本”页。

    1.  在“安装脚本”中键入脚本文件的位置，或选择省略号 (…) 以找到安装脚本。

    2.  在“清理脚本”中键入脚本文件的位置，或选择省略号 (…) 以找到清理脚本。

24. 若要使用其他主机运行测试，请选择“主机”。

    1.  在“主机类型”中，验证是否已选中“默认”。

        > [!NOTE]
        > “主机类型”中的“ASP.NET”在负载测试中不受支持。

    2.  使用“在 32 或 64 位进程中运行测试”下拉列表选择希望负载测试中的 Web 性能和单元测试作为 32 位还是 64 位进程运行。

        > [!NOTE]
        > 为了最大限度地提高灵活性，应使用“任何 CPU”配置来编译 Web 性能和负载测试项目。 然后，可以在 32 位和 64 位代理上运行。 使用“64 位”配置编译 Web 性能和负载测试项目没有任何优势。

25. （可选）若要限制每个测试运行和各个测试的时间，请选择“测试超时”。

    1.  若要在超过一定时间限制时中止测试运行，请选择“在总执行时间超过以下值时中止测试运行”，然后键入此时限的值。

    2.  若要在超过一定时限时使单个测试未通过，请选择“在单个测试的执行用时超过以下值时，将其标记为未通过”，然后键入此时限的值。

26. 跳过“单元测试”。 负载测试不使用这些设置。

27. 跳过“Web 测试”。 负载测试不使用这些设置。

28. 若要保存测试设置，请选择“另存为”。 在“对象名称”中键入所需文件的名称。

    > [!NOTE]
    > 如果必须更改测试设置，请选择“测试”，然后选择“编辑测试设置”并指向所创建的测试设置。

### <a name="to-remove-a-test-settings-from-your-solution"></a>从解决方案中移除测试设置

在“解决方案资源管理器”中的“解决方案项”文件夹下，右键单击要删除的测试设置，然后选择“删除”。

该测试设置文件随即从解决方案中移除。 “测试”菜单上的“选择活动的测试设置”和“编辑测试设置”选项的选择列表中将反映此更改。

## <a name="see-also"></a>请参阅

- [测试控制器和测试代理](configure-test-agents-and-controllers-for-load-tests.md)
- [使用测试设置收集诊断信息](../test/collect-diagnostic-information-using-test-settings.md)