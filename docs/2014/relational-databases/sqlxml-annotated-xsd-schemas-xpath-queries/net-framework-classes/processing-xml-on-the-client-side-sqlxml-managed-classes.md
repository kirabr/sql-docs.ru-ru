---
title: Обработка XML-кода на стороне клиента (управляемые классы SQLXML) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- processing XML on client side [SQLXML]
- client-side XML formatting
- Managed Classes [SQLXML], client-side XML formatting
- SQLXML Managed Classes, client-side XML formatting
- ClientSideXml property
ms.assetid: 5e7ecf18-66fc-49ff-bc50-83635cd7ac0b
caps.latest.revision: 21
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 242e06d72b7a1773235e51c7211b2526af6d4608
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37201104"
---
# <a name="processing-xml-on-the-client-side-sqlxml-managed-classes"></a>Обработка XML-кода на стороне клиента (управляемые классы SQLXML)
  В этом примере показано использование свойства ClientSideXml. Приложение выполняет хранимую процедуру на сервере. Результат хранимой процедуры (набор строк из двух столбцов) обрабатывается на стороне клиента для создания XML-документа.  
  
 Следующие GetContacts хранимая процедура возвращает **FirstName** и **LastName** сотрудников из таблицы Person.Contact в базе данных AdventureWorks.  
  
```  
USE AdventureWorks  
CREATE PROCEDURE GetContacts @LastName varchar(20)  
AS  
SELECT FirstName, LastName  
FROM   Person.Contact  
WHERE LastName = @LastName  
Go  
```  
  
 Это приложение C# выполняет хранимую процедуру и задает параметр FOR XML AUTO при указании значение CommandText. В приложении, ClientSideXml SqlXmlCommand объекта свойству значение true. Это позволяет выполнять существующие хранимые процедуры, возвращающие наборы строк, и применить к ним преобразование XML на стороне клиента.  
  
> [!NOTE]  
>  В коде необходимо задать имя экземпляра Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
    static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         //Stream strm;  
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.ClientSideXml = true;  
         cmd.CommandText = "EXEC GetContacts ? FOR XML NESTED";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         using (Stream strm = cmd.ExecuteStream())   
         {  
            using (StreamReader sr = new StreamReader(strm))  
                  {  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;  
      }  
  
public static int Main(String[] args)  
{  
    testParams();  
    return 0;  
}  
}  
```  
  
 Чтобы проверить этот пример, необходимо установить на компьютер платформу [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.  
  
### <a name="to-test-the-application"></a>Тестирование приложения  
  
1.  Создайте хранимую процедуру.  
  
2.  Сохраните в папке код C# (файл DocSample.cs), приведенный в этом примере. Измените этот код, указав нужные имя входа и пароль.  
  
3.  Скомпилируйте код. Чтобы скомпилировать код из командной строки, введите следующую команду.  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     Будет создан исполняемый файл (DocSample.exe).  
  
4.  Запустите файл DocSample.exe из командной строки.  
  
  
