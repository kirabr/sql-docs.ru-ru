---
title: sys.fn_virtualfilestats (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 08/16/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: system-functions
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- fn_virtualfilestats_TSQL
- fn_virtualfilestats
dev_langs:
- TSQL
helpviewer_keywords:
- I/O [SQL Server], statistics
- fn_virtualfilestats function
- sys.fn_virtualfilestats function
- statistical information [SQL Server], I/O
ms.assetid: 96b28abb-b059-48db-be2b-d60fe127f6aa
caps.latest.revision: 29
author: rothja
ms.author: jroth
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: f8e8bf556d721ac18af7fa552db558395bff76f2
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43090992"
---
# <a name="sysfnvirtualfilestats-transact-sql"></a>sys.fn_virtualfilestats (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Возвращает статистику ввода-вывода для файлов базы данных, включая файлы журналов. В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], эта информация также доступна из [sys.dm_io_virtual_file_stats](../../relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql.md) динамическое административное представление.  

 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
fn_virtualfilestats ( { database_id | NULL } , { file_id | NULL } )  
```  
  
## <a name="arguments"></a>Аргументы  
 *database_id* | ЗНАЧЕНИЕ NULL  
 Идентификатор базы данных. Аргумент *database_id* имеет тип **int** и не имеет значения по умолчанию. Укажите значение NULL, чтобы вернуть сведения для всех баз данных в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 *file_id* | ЗНАЧЕНИЕ NULL  
 Идентификатор файла. *file_id* — **int**, не имеет значения по умолчанию. Чтобы получить сведения обо всех файлах в базе данных, укажите значение NULL.  
  
## <a name="table-returned"></a>Возвращаемая таблица  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**DbId**|**smallint**|Идентификатор базы данных.|  
|**FileId**|**smallint**|Идентификатор файла.|  
|**Метка времени**|**bigint**|Отметка времени базы данных, указывающая, когда была получена информация. **int** в версиях до [!INCLUDE[ssSQL15_md](../../includes/sssql15-md.md)]. |  
|**Количество запросов на чтение**|**bigint**|Количество считываний для этого файла.|  
|**BytesRead**|**bigint**|Число считанных из файла байтов.|  
|**IoStallReadMS**|**bigint**|Общее количество времени, в миллисекундах, затраченного пользователями на ожидание выполнения операций чтения из файла.|  
|**Количество запросов на запись**|**bigint**|Количество операций записи для этого файла.|  
|**Записано байт**|**bigint**|Число байтов, записанных в файл.|  
|**IoStallWriteMS**|**bigint**|Общее количество времени, в миллисекундах, затраченного пользователями на ожидание выполнения операций записи в файл.|  
|**IoStallMS**|**bigint**|Сумма **IoStallReadMS** и **IoStallWriteMS**.|  
|**FileHandle**|**bigint**|Значение дескриптора файла.|  
|**BytesOnDisk**|**bigint**|Физический размер файла на диске (в байтах).<br /><br /> Для файлов базы данных, это то же значение, что **размер** в **sys.database_files**, но выражается в байтах, а не страницы.<br /><br /> Для разреженных файлов моментального снимка базы данных это пространство, используемое операционной системой для данного файла.|  
  
## <a name="remarks"></a>Примечания  
 **fn_virtualfilestats** — это система, возвращающих табличные значения функция, которая дает статистическую информацию, например общее количество операций ввода-вывода, выполненных над файлом. Эту функцию можно использовать для контроля времени, затрачиваемого пользователями на ожидание выполнения чтения или записи в файл. Эта функция также помогает выявить файлы, над которыми выполняется много операций ввода-вывода.  
  
## <a name="permissions"></a>Разрешения  
 необходимо разрешение VIEW SERVER STATE на сервере.  
  
## <a name="examples"></a>Примеры  
  
### <a name="a-displaying-statistical-information-for-a-database"></a>A. Просмотр статистической информации для базы данных  
 В следующем примере выводится статистическая информация для идентификатора файла 1 в базе данных с идентификатором `1`.  
  
```sql  
SELECT *  
FROM fn_virtualfilestats(1, 1);  
GO  
```  
  
### <a name="b-displaying-statistical-information-for-a-named-database-and-file"></a>Б. Просмотр статистической информации для именованной базы данных и файла  
 В следующем примере выводятся статистические данные для файла журнала в образце базы данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)]. Системная функция `DB_ID` используется для указания *database_id* параметра.  
  
```sql  
SELECT *  
FROM fn_virtualfilestats(DB_ID(N'AdventureWorks2012'), 2);  
GO  
```  
  
### <a name="c-displaying-statistical-information-for-all-databases-and-files"></a>В. Просмотр статистической информации для всех баз данных и файлов  
 В следующем примере выводится статистическая информация для всех файлов во всех базах данных экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
```sql  
SELECT *  
FROM fn_virtualfilestats(NULL,NULL);  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [DB_ID &#40;Transact-SQL&#41;](../../t-sql/functions/db-id-transact-sql.md)   
 [FILE_IDEX (Transact-SQL)](../../t-sql/functions/file-idex-transact-sql.md)   
 [sys.database_files (Transact-SQL)](../../relational-databases/system-catalog-views/sys-database-files-transact-sql.md)   
 [sys.master_files (Transact-SQL)](../../relational-databases/system-catalog-views/sys-master-files-transact-sql.md)  
  
  
