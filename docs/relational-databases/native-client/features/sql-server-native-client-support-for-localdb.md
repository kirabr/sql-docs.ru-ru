---
title: Поддержка SQL Server Native Client для LocalDB | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 127569d1-a9f7-49bf-a561-c084986a8871
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: b162147144e403623d46d96bcdf0060e9e5e01ac
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43093898"
---
# <a name="sql-server-native-client-support-for-localdb"></a>Поддержка SQL Server Native Client для LocalDB
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  Начиная с версии [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], будет доступна облегченная версия SQL Server, называемая LocalDB. В этом разделе обсуждается, как можно установить соединение с базой данных на экземпляре LocalDB.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о LocalDB, включая способы его установки и настройки, см. в разделе:  
  
-   [Справочник по SQL Server Express LocalDB](../../../relational-databases/sql-server-express-localdb-reference.md)  
  
-   [SQL Server 2016 Express LocalDB](../../../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
 LocalDB позволяет выполнять следующие действия.  
  
-   Использовать программу **sqllocaldb.exe i** для поиска имени экземпляра по умолчанию.  
  
-   Использовать ключевое слово строки подключения **AttachDBFilename** для указания файла базы данных, который сервер должен присоединить. Если при использовании **AttachDBFilename**не указано имя базы данных в ключевом слове строки подключения **Database** , то база данных будет удалена из экземпляра LocalDB при закрытии приложения.  
  
-   Чтобы указать экземпляр LocalDB в строке подключения, выполните следующие действия.  
  
```  
SERVER=(localdb)\v11.0  
```  
  
 При необходимости можно создать экземпляр LocalDB с помощью программы sqllocaldb.exe. Для добавления и изменения баз данных в локальном экземпляре LocalDB можно также воспользоваться программой sqlcmd.exe. Например, **sqlcmd -S (localdb)\v11.0**.  
  
## <a name="see-also"></a>См. также  
 [Компоненты SQL Server Native Client](../../../relational-databases/native-client/features/sql-server-native-client-features.md)  
  
  
