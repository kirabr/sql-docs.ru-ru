---
title: Использование SQL Server по умолчанию результирующих наборов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQLSetStmtAttr function
- ODBC cursors, default result sets
- cursors [ODBC], default result sets
- default result sets
- result sets [ODBC], default
- ODBC applications, cursors
ms.assetid: ee1db3e5-60eb-4425-8a6b-977eeced3f98
caps.latest.revision: 35
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 7a4ad5f55da7e5188b4555fbbfe3c4a3fabdc3ae
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37415016"
---
# <a name="using-sql-server-default-result-sets"></a>Использование результирующих наборов по умолчанию в SQL Server
  Атрибутами курсора ODBC по умолчанию являются:  
  
```  
SQLSetStmtAttr(hstmt, SQL_ATTR_CURSOR_TYPE, SQL_CURSOR_FORWARD_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_CONCURRENCY, SQL_CONCUR_READ_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_ARRAY_SIZE, 1, SQL_IS_INTEGER);  
```  
  
 Каждый раз, когда эти атрибуты имеют значения по умолчанию, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] использует драйвер ODBC собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] результирующий набор по умолчанию. Результирующие наборы по умолчанию могут использоваться для любой инструкции SQL, поддерживаемой [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], и являются самым эффективным методом передачи всего результирующего набора клиенту.  
  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] введена поддержка множественных активных результирующих наборов (MARS); Теперь приложения могут иметь более одного активного результирующего набора в расчете на соединение. По умолчанию режим MARS не включен.  
  
 До версии [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] принимаемые по умолчанию результирующие наборы не поддерживали несколько активных инструкций для одного соединения. После выполнения инструкции SQL для соединения сервер не принимает команд от клиента в этом соединении до тех пор, пока не будут обработаны все строки результирующего набора. Исключение составляют запросы на отмену оставшейся части результирующего набора. Для отмены оставшейся части частично обработанного результирующего набора, вызовите [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) или [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) с *fOption* параметр значение SQL_CLOSE. Чтобы завершить частично обработанного результирующего набора и тестирования на наличие другой результирующий набор, вызвать [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md). Если приложение ODBC пытается выполнить команду над дескриптором соединения перед результирующим набором по умолчанию полностью обработаны, вызов приводит к возникновению ошибки SQL_ERROR и вызов **SQLGetDiagRec** возвращает:  
  
```  
szSqlState: "HY000", pfNativeError: 0  
szErrorMsg: "[Microsoft][SQL Server Native Client]  
                Connection is busy with results for another hstmt."  
```  
  
## <a name="see-also"></a>См. также  
 [Способы реализации курсоров](how-cursors-are-implemented.md)  
  
  
