---
title: Использование синонимов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- synonyms [SMO]
ms.assetid: db0a9022-9549-43e5-b6b3-deb236f05fb8
caps.latest.revision: 47
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 3776dfb8c6bf59e83543089359d9a80a8ea5ebc5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37202984"
---
# <a name="using-synonyms"></a>Использование синонимов
  Синоним — это альтернативное имя, которое дается объекту в области схемы. В SMO синонимы представлены <xref:Microsoft.SqlServer.Management.Smo.Synonym> объекта. Объект <xref:Microsoft.SqlServer.Management.Smo.Synonym> является дочерним для объекта <xref:Microsoft.SqlServer.Management.Smo.Database>. Это означает, что синонимы действительны только в пределах базы данных, в которой они определены. Однако синоним может относиться к объектам на другую базу данных или на удаленном экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 Объект, которому дано альтернативное имя, известен как базовый объект. Свойство имени объекта <xref:Microsoft.SqlServer.Management.Smo.Synonym> служит альтернативным именем базового объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере кода для создания приложения необходимо выбрать среду программирования, шаблон программирования и язык программирования. Дополнительные сведения см. в разделе [Создание проекта SMO на Visual Basic в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) и [Visual C создайте&#35; проекта SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).  
  
## <a name="creating-a-synonym-in-visual-basic"></a>Создание синонима на языке Visual Basic  
 Этот пример кода показывает, как создать синоним или альтернативное имя для объекта из области схемы. Клиентские приложения для ссылки на базовый объект могут использовать одну ссылку на него через синоним вместо использования имени, состоящего из нескольких частей.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBSynonyms1](SMO How to#SMO_VBSynonyms1)]  -->  
  
## <a name="creating-a-synonym-in-visual-c"></a>Создание синонима на языке Visual C#  
 Этот пример кода показывает, как создать синоним или альтернативное имя для объекта из области схемы. Клиентские приложения для ссылки на базовый объект могут использовать одну ссылку на него через синоним вместо использования имени, состоящего из нескольких частей.  
  
```  
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Synonym object variable by supplying the   
            //parent database, name, and schema arguments in the constructor.   
            //The name is also a synonym of the name of the base object.   
            Synonym syn = new Synonym(db, "Shop", "Sales");  
  
            //Specify the base object, which is the object on which   
            //the synonym is based.   
            syn.BaseDatabase = "AdventureWorks2012";  
            syn.BaseSchema = "Sales";  
            syn.BaseObject = "Store";  
            syn.BaseServer = srv.Name;  
  
            //Create the synonym on the instance of SQL Server.   
            syn.Create();  
        }  
```  
  
## <a name="creating-a-synonym-in-powershell"></a>Создание синонима в PowerShell  
 Этот пример кода показывает, как создать синоним или альтернативное имя для объекта из области схемы. Клиентские приложения для ссылки на базовый объект могут использовать одну ссылку на него через синоним вместо использования имени, состоящего из нескольких частей.  
  
```  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#And the database object corresponding to Adventureworks  
$db = $srv.Databases["AdventureWorks2012"]  
  
$syn = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Synonym `  
-argumentlist $db, "Shop", "Sales"  
  
#Specify the base object, which is the object on which the synonym is based.  
$syn.BaseDatabase = "AdventureWorks2012"  
$syn.BaseSchema = "Sales"  
$syn.BaseObject = "Store"  
$syn.BaseServer = $srv.Name  
  
#Create the synonym on the instance of SQL Server.  
$syn.Create()  
```  
  
## <a name="see-also"></a>См. также  
 [CREATE SYNONYM (Transact-SQL)](/sql/t-sql/statements/create-synonym-transact-sql)  
  
  
