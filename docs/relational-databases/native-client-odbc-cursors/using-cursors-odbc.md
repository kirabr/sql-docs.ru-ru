---
title: Использование курсоров (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC]
- ODBC cursors
ms.assetid: 51322f92-0d76-44c9-9c33-9223676cf1d3
caps.latest.revision: 36
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 319ebd5a53360beb4b909b5b9d0a5a623020e1b8
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43111261"
---
# <a name="using-cursors-odbc"></a>Использование курсоров (ODBC)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  ODBC поддерживает модель курсора, которая позволяет следующее.  
  
-   Несколько типов курсоров.  
  
-   Прокрутку и позиционирование в курсоре.  
  
-   Несколько параметров параллелизма.  
  
-   Позиционированные обновления.  
  
 Приложения ODBC редко декларируют и открывают курсоры или используют любые связанные с курсорами инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)]. ODBC автоматически открывает курсор для каждого возвращенного результирующего набора из инструкции SQL. Характеристики курсоров управляются атрибуты инструкции, набор с [SQLSetStmtAttr](../../relational-databases/native-client-odbc-api/sqlsetstmtattr.md) перед SQL выполняется инструкция. Функции API ODBC для обработки результирующих наборов поддерживают полный набор функций работы с курсором, включая выборку, прокрутку и позиционированные обновления.  
  
 Далее приведено сравнение работы с курсорами в скриптах [!INCLUDE[tsql](../../includes/tsql-md.md)] и приложениях ODBC.  
  
|Действие|[!INCLUDE[tsql](../../includes/tsql-md.md)]|интерфейс ODBC|  
|------------|------------------------|----------|  
|Определение режима работы курсоров|Указание через параметры DECLARE CURSOR|Присвоить атрибутам курсора с помощью [SQLSetStmtAttr](../../relational-databases/native-client-odbc-api/sqlsetstmtattr.md)|  
|Открытие курсора|DECLARE CURSOR OPEN *cursor_name*|**SQLExecDirect** или **SQLExecute**|  
|Выборка строк|FETCH|**SQLFetch** или [SQLFetchScroll](../../relational-databases/native-client-odbc-api/sqlfetchscroll.md)|  
|Позиционированное обновление|Предложение WHERE CURRENT OF для инструкции UPDATE или DELETE.|**SQLSetPos**|  
|Закрытие курсора|ЗАКРЫТЬ *cursor_name* DEALLOCATE|[SQLCloseCursor](../../relational-databases/native-client-odbc-api/sqlclosecursor.md)|  
  
 Серверные курсоры, реализованные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], поддерживают функции модели курсора ODBC. Драйвер для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует серверные курсоры для поддержки функций работы с курсорами API ODBC.  
  
## <a name="in-this-section"></a>в этом разделе  
  
-   [Способы реализации курсоров](../../relational-databases/native-client-odbc-cursors/implementation/how-cursors-are-implemented.md)  
  
-   [Типы курсоров](../../relational-databases/native-client-odbc-cursors/cursor-types.md)  
  
-   [Режимы работы курсоров](../../relational-databases/native-client-odbc-cursors/cursor-behaviors.md)  
  
-   [Свойства курсора](../../relational-databases/native-client-odbc-cursors/properties/cursor-properties.md)  
  
-   [Подробные сведения о программировании курсоров &#40;ODBC&#41;](../../relational-databases/native-client-odbc-cursors/programming/cursor-programming-details-odbc.md)  
  
-   [Прокрутка и выборка строк](../../relational-databases/native-client-odbc-cursors/scrolling-and-fetching-rows.md)  
  
-   [Позиционированные обновления &#40;ODBC&#41;](../../relational-databases/native-client-odbc-cursors/positioned-updates-odbc.md)  
  
## <a name="see-also"></a>См. также  
 [Собственный клиент SQL Server &#40;ODBC&#41;](../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)   
 [CLOSE (Transact-SQL)](../../t-sql/language-elements/close-transact-sql.md)   
 [Курсоры](../../relational-databases/cursors.md)   
 [DEALLOCATE (Transact-SQL)](../../t-sql/language-elements/deallocate-transact-sql.md)   
 [DECLARE CURSOR (Transact-SQL)](../../t-sql/language-elements/declare-cursor-transact-sql.md)   
 [FETCH (Transact-SQL)](../../t-sql/language-elements/fetch-transact-sql.md)   
 [OPEN (Transact-SQL)](../../t-sql/language-elements/open-transact-sql.md)  
  
  
