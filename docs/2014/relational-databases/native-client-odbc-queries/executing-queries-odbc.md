---
title: Выполнение запросов (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ODBC applications, executing queries
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
- SQL Server Native Client ODBC driver, queries
- queries [ODBC]
ms.assetid: d935bcba-8ce6-4159-8395-6c86431602ad
caps.latest.revision: 31
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 552a9d37d06ba145e371650dd56027ca38eb7c20
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37416283"
---
# <a name="executing-queries-odbc"></a>Выполнение запросов (ODBC)
  После того, как приложение ODBC инициализирует дескриптор соединения и подключается к источнику данных, оно выделяет один или несколько дескрипторов инструкций на дескриптор соединения. Приложение может затем выполнить [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] инструкций с дескриптором инструкции. Общая последовательность событий при выполнении инструкции SQL.  
  
1.  Установите необходимые атрибуты инструкции.  
  
2.  Сформируйте инструкцию.  
  
3.  Выполните инструкцию.  
  
4.  Получите результирующие наборы.  
  
 После того, как приложение получит все строки во всех результирующих наборах, возвращенных инструкцией SQL, оно может выполнить другой запрос на том же дескрипторе инструкции. Если приложение определяет, что он не требуется извлекать все строки в некотором результирующем наборе, его можно отменить остаток результирующего набора с помощью вызова [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) или [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).  
  
 Если в приложении ODBC необходимо несколько раз выполнить одну инструкцию SQL с различными данными, используйте маркер параметра, обозначенный вопросительным знаком (?) при построении инструкции SQL:  
  
```  
INSERT INTO MyTable VALUES (?, ?, ?)  
```  
  
 Каждый маркер параметра затем подключаются к программной переменной путем вызова [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).  
  
 После того, как будут вызваны все инструкции SQL и обработаны их результирующие наборы, приложение освобождает дескриптор инструкции.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Драйвер ODBC для собственного клиента поддерживает несколько дескрипторов инструкций на один дескриптор соединения. Управление транзакциями осуществляется на уровне соединения, поэтому вся работа, выполняемая со всеми дескрипторами инструкций на одном дескрипторе соединения, управляется как часть одной транзакции.  
  
## <a name="in-this-section"></a>в этом разделе  
  
-   [Выделение дескриптора инструкции](allocating-a-statement-handle.md)  
  
-   [Конструирование инструкций SQL &#40;ODBC&#41;](constructing-an-sql-statement-odbc.md)  
  
-   [Конструирование инструкций SQL для курсоров](constructing-sql-statements-for-cursors.md)  
  
-   [Использование параметров инструкции](using-statement-parameters.md)  
  
-   [Выполнение инструкций &#40;ODBC&#41;](executing-statements/executing-statements-odbc.md)  
  
-   [Освобождение дескриптора инструкции](freeing-a-statement-handle.md)  
  
## <a name="see-also"></a>См. также  
 [SQL Server Native Client (ODBC)](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
