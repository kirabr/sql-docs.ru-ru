---
title: Объект SqlDataRecord | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.suite: sql
ms.technology: clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SqlDataRecord object
- custom result sets [CLR integration]
ms.assetid: 2ed667fb-749c-4280-a8fb-650643683c8f
caps.latest.revision: 25
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: eed4ff836262fdf9a2a0cbb4d48e7b9fc7c4b94a
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37359926"
---
# <a name="sqldatarecord-object"></a>Объект SqlDataRecord
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Объект **SqlDataRecord** представляет одну строку данных и связанные с ними метаданные.  
  
 Управляемые хранимые процедуры могут отправлять результирующие наборы, которые не относятся к **SqlDataReader**. Класс **SqlDataRecord** вместе с методами **SendResultsStart**, **SendResultsRow**и **SendResultsEnd** объекта **SqlPipe** позволяет хранимым процедурам отправлять клиенту пользовательские результирующие наборы.  
  
 Дополнительные сведения см. в справочной документации по классу **Microsoft.SqlServer.Server.SqlDataRecord** в документации по пакету .NET Framework SDK.  
  
## <a name="example"></a>Пример  
 В следующем примере создается новая запись сотрудника, которая возвращается вызывающему.  
  
 C#  
  
```  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void CreateNewRecordProc()  
{  
    // Variables.         
    SqlDataRecord record;  
  
    // Create a new record with the column metadata.  The constructor   
    // is able to accept a variable number of parameters.  
    record = new SqlDataRecord(new SqlMetaData("EmployeeID", SqlDbType.Int),  
                               new SqlMetaData("Surname", SqlDbType.NVarChar, 20),  
                               new SqlMetaData("GivenName", SqlDbType.NVarChar, 20),  
                               new SqlMetaData("StartDate", SqlDbType.DateTime) );  
  
    // Set the record fields.  
    record.SetInt32(0, 0042);  
    record.SetString(1, "Funk");  
    record.SetString(2, "Don");  
    record.SetDateTime(3, new DateTime(2005, 7, 17));  
  
    // Send the record to the calling program.  
    SqlContext.Pipe.Send(record);  
  
}  
```  
  
 Visual Basic  
  
```  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  CreateNewRecordVBProc ()  
    ' Variables.  
    Dim record As SqlDataRecord  
  
    ' Create a new record with the column metadata. The constructor is   
    ' able to accept a variable number of parameters  
  
    record = New SqlDataRecord(New SqlMetaData("EmployeeID", SqlDbType.Int), _  
                           New SqlMetaData("Surname", SqlDbType.NVarChar, 20), _  
                           New SqlMetaData("GivenName", SqlDbType.NVarChar, 20), _  
                           New SqlMetaData("StartDate", SqlDbType.DateTime))  
  
    ' Set the record fields.  
    record.SetInt32(0, 42)  
    record.SetString(1, "Funk")  
    record.SetString(2, "Don")  
    record.SetDateTime(3, New DateTime(2005, 7, 17))  
  
    ' Send the record to the calling program.  
    SqlContext.Pipe.Send(record)  
  
End Sub  
```  
  
## <a name="see-also"></a>См. также  
 [Объект SqlPipe](../../relational-databases/clr-integration-data-access-in-process-ado-net/sqlpipe-object.md)  
  
  
