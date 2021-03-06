---
title: CHANGE_TRACKING_MIN_VALID_VERSION (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 08/08/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: system-functions
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- CHANGE_TRACKING_CLEANUP_VERSION
- CHANGE_TRACKING_CLEANUP_VERSION_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- CHANGE_TRACKING_MIN_VALID_VERSION
- change tracking [SQL Server], CHANGE_TRACKING_MIN_VALID_VERSION
ms.assetid: 5a43d23f-adcf-4c0b-95ad-07cee03c1f9d
caps.latest.revision: 16
author: rothja
ms.author: jroth
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 0a37a969a2a5e0f7cfb6586549e78eb8b36c4fa0
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43062976"
---
# <a name="changetrackingminvalidversion-transact-sql"></a>CHANGE_TRACKING_MIN_VALID_VERSION (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Возвращает минимальную версию клиента, которое является допустимым для получения данных отслеживания изменений из указанной таблицы, при использовании [CHANGETABLE](../../relational-databases/system-functions/changetable-transact-sql.md) функции.  
    
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
CHANGE_TRACKING_MIN_VALID_VERSION ( table_object_id )  
```  
  
## <a name="arguments"></a>Аргументы  
 *table_object_id*  
 Объектный идентификатор таблицы. *table_object_id* — **int**.  
  
## <a name="return-type"></a>Тип возвращаемых данных  
 **bigint**  
  
## <a name="remarks"></a>Примечания  
 Эта функция используется для проверки значения *last_sync_version* параметра для функции CHANGETABLE. Если *last_sync_version* меньше, чем значения, возвращаемого этой функцией, результаты, возвращаемые последующим вызовом CHANGETABLE могут оказаться недопустимыми.  
  
 Функция CHANGE_TRACKING_MIN_VALID_VERSION использует для определения значения возврата следующие сведения.  
  
-   Когда было включено отслеживание изменений для таблицы.  
  
-   Когда была выполнена задача фоновой очистки для удаления данных отслеживания изменений, срок хранения которых превысил срок хранения, указанный для базы данных.  
  
-   Была ли таблица усечена. При этом удаляются все данные отслеживания изменений, связанные с таблицей.  
  
 Функция возвращает значение NULL, если любое из следующих условий верно.  
  
-   Отслеживание изменений для базы данных не включено.  
  
-   Указанный идентификатор объекта таблицы для текущей базы данных недопустим.  
  
-   Недостаточно разрешений для таблицы, указанной идентификатором объекта.  
  
## <a name="examples"></a>Примеры  
 В следующем примере определяется, является ли указанная версия допустимой. В примере получается минимально допустимая версия таблицы `dbo.Employees`, а затем это значение сравнивается со значением переменной `@last_sync_version`. Если значение `@last_sync_version` меньше, чем значение переменной `@min_valid_version`, список измененных строк недопустим.  
  
> [!NOTE]  
>  Обычно это значение получается из таблицы или другого места, в котором хранится номер последней версии, использованной для синхронизации данных.  
  
```  
-- The tracked change is tagged with the specified context   
DECLARE @min_valid_version bigint, @last_sync_version bigint;  
  
SET @min_valid_version =   
CHANGE_TRACKING_MIN_VALID_VERSION(OBJECT_ID('dbo.Employees'));  
  
SET @last_sync_version = 11  
IF (@last_sync_version < @min_valid_version)  
-- Error � do not obtain changes  
ELSE  
-- Obtain changes using CHANGETABLE(CHANGES ...)  
```  
  
## <a name="see-also"></a>См. также  
 [Функции отслеживания изменений (Transact-SQL)](../../relational-databases/system-functions/change-tracking-functions-transact-sql.md)   
 [sys.change_tracking_tables (Transact-SQL)](../../relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables.md)  
  
  
