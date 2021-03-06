---
title: 演示示例 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
caps.latest.revision: 23
author: corob-msft
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5bcdb1e026808071167b23b829597a4d28775c02
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49880645"
---
# <a name="demo-sample"></a>演示示例
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

以下过程演示如何创建的示例[演练： 分析 C/c + + 代码缺陷](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md)。 这些过程将创建：  
  
- 一个[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]名为 CppDemo 解决方案。  
  
- 静态库项目命名为 CodeDefects。  
  
- 静态库项目命名为批注。  
  
  过程还会提供代码的静态库的标头和.cpp 文件。  
  
### <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>创建 CppDemo 解决方案和 CodeDefects 项目  
  
1.  单击**文件**菜单，依次指向**新建**，然后单击**新项目**。  
  
2.  在中**项目类型**树列表中，如果在 VS 中的默认语言不是 Visual c + + 扩展**其他语言**。  
  
3.  展开**Visual c + +**，然后单击**常规**。  
  
4.  在中**模板**，单击**空项目**。  
  
5.  在中**名称**文本框中，键入**CodeDefects**。  
  
6.  选择**创建解决方案目录**复选框。  
  
7.  在中**解决方案名称**文本框中，键入**CppDemo**。  
  
### <a name="configure-the-codedefects-project-as-a-static-library"></a>CodeDefects 项目配置为静态库  
  
1.  在解决方案资源管理器中右键单击**CodeDefects** ，然后单击**属性**。  
  
2.  展开**配置属性**，然后单击**常规**。  
  
3.  在中**常规**列表中，选择列中的文本旁边**目标扩展名**，然后键入 **.lib**。  
  
4.  在中**项目默认值**，单击旁边的列**配置类型**，然后单击**静态库 (.lib)**。  
  
### <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>将标头和源代码文件添加到 CodeDefects 项目  
  
1.  在解决方案资源管理器，展开**CodeDefects**，右键单击**头文件**，单击**添加**，然后单击**新项**。  
  
2.  在中**添加新项**对话框中，单击**代码**，然后单击**标头文件 (.h)**。  
  
3.  在中**名称**框中，键入**Bug.cpp** ，然后单击**添加**。  
  
4.  将以下代码复制并将其粘贴到**Bug.cpp**文件中[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]编辑器。  
  
    ```  
    #include <windows.h>  
  
    //    
    //These 3 functions are consumed by the sample  
    //  but are not defined. This project cannot be linked!  
    //  
  
    bool CheckDomain( LPCSTR );  
    HRESULT ReadUserAccount();  
  
    //  
    //These constants define the common sizes of the   
    //  user account information throughout the program  
    //  
  
    const int USER_ACCOUNT_LEN = 256;  
    const int ACCOUNT_DOMAIN_LEN = 128;  
    ```  
  
5.  在解决方案资源管理器中右键单击**源文件**，依次指向**新建**，然后单击**新项**。  
  
6.  在中**添加新项**对话框中，单击**c + + 文件 (.cpp)**  
  
7.  在中**名称**框中，键入**Bug.cpp** ，然后单击**添加**。  
  
8.  将以下代码复制并粘贴到中的 Bug.h 文件[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]编辑器。  
  
    ```  
    #include <stdlib.h>  
    #include "Bug.h"  
  
    // the user account   
    TCHAR g_userAccount[USER_ACCOUNT_LEN] = "";  
    int len = 0;  
  
    bool ProcessDomain()  
    {  
        TCHAR* domain = new TCHAR[ACCOUNT_DOMAIN_LEN];  
        // ReadUserAccount gets a 'domain\user' input from   
        //the user into the global 'g_userAccount'  
        if (ReadUserAccount() )  
        {  
  
            // Copies part of the string prior to the '\'   
            // character onto the 'domain' buffer  
            for( len = 0 ; (len < ACCOUNT_DOMAIN_LEN) && (g_userAccount[len] != '\0') ; len++  )  
            {  
                if ( g_userAccount[len] == '\\' )   
                {  
                    // Stops copying on the domain and user separator ('\')   
                    break;  
                }  
                domain[len] = g_userAccount[len];          
            }  
            if((len= ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != '\\'))  
            {  
                // '\' was not found. Invalid domain\user string.  
                delete [] domain;  
                return false;  
            }  
            else  
            {  
                domain[len]='\0';  
            }  
            // Process domain string  
            bool result = CheckDomain( domain );  
  
            delete[] domain;  
            return result;  
        }  
        return false;  
    }  
  
    int path_dependent(int n)  
    {  
        int i;  
        int j;  
        if (n == 0)  
            i = 1;  
        else  
            j = 1;  
        return i+j;   
    }  
    ```  
  
9. 单击**文件**菜单，并单击**全部保存**。  
  
### <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>添加批注项目并将其配置为静态库  
  
1.  在解决方案资源管理器，单击**CppDemo**，依次指向**添加**，然后单击**新项目**。  
  
2.  在中**添加新项目**对话框框中，展开 Visual c + + 中，单击**常规**，然后单击**空项目**。  
  
3.  在中**名称**文本框中，键入**批注**，然后单击**添加**。  
  
4.  在解决方案资源管理器中右键单击**批注**，然后单击**属性**。  
  
5.  展开**配置属性**，然后单击**常规**。  
  
6.  在中**常规**列表中，选择列中的文本旁边**目标扩展名**，然后键入 **.lib**。  
  
7.  在中**项目默认值**，单击旁边的列**配置类型**，然后单击**静态库 (.lib)**。  
  
### <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>将标头文件和源文件添加到批注项目  
  
1.  在解决方案资源管理器，展开**批注**，右键单击**头文件**，单击**添加**，然后单击**新项**。  
  
2.  在中**添加新项**对话框中，单击**标头文件 (.h)**。  
  
3.  在中**名称**框中，键入**annotations.h** ，然后单击**添加**。  
  
4.  将以下代码复制并将其粘贴到**annotations.h**文件中[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]编辑器。  
  
    ```  
    #include <CodeAnalysis/SourceAnnotations.h>  
  
    struct LinkedList  
    {  
        struct LinkedList* next;  
        int data;  
    };  
  
    typedef struct LinkedList LinkedList;  
  
    [returnvalue:SA_Post( Null=SA_Maybe )] LinkedList* AllocateNode();  
  
    ```  
  
5.  在解决方案资源管理器中右键单击**源文件**，依次指向**新建**，然后单击**新项**。  
  
6.  在中**添加新项**对话框中，单击**代码**，然后单击**c + + 文件 (.cpp)**  
  
7.  在中**名称**框中，键入**annotations.cpp** ，然后单击**添加**。  
  
8.  将以下代码复制并将其粘贴到**annotations.cpp**文件中[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]编辑器。  
  
    ```  
    #include <CodeAnalysis/SourceAnnotations.h>  
    #include <windows.h>  
    #include <stdlib.h>    
    #include "annotations.h"  
  
    LinkedList* AddTail( LinkedList *node, int value )  
    {  
        LinkedList *newNode = NULL;   
  
        // finds the last node  
        while ( node->next != NULL )   
        {  
            node = node->next;  
        }  
  
        // appends the new node  
        newNode = AllocateNode();   
        newNode->data = value;  
        newNode->next = 0;  
        node->next = newNode;  
  
        return newNode;  
    }  
  
    ```  
  
9. 单击**文件**菜单，并单击**全部保存**。



