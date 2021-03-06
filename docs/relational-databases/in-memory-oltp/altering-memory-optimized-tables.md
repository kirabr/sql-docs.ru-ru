---
title: Изменение оптимизированных для памяти таблиц | Документация Майкрософт
ms.custom: ''
ms.date: 06/19/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: in-memory-oltp
ms.reviewer: ''
ms.suite: sql
ms.technology: in-memory-oltp
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 690b70b7-5be1-4014-af97-54e531997839
caps.latest.revision: 20
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: da66b05181d2d4394bd0dfa83354c01e6d05af08
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43111829"
---
# <a name="altering-memory-optimized-tables"></a>Изменение таблиц с оптимизацией для памяти
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

  Изменения схемы и индекса в таблицах, оптимизированных для памяти, можно выполнить с помощью инструкции ALTER TABLE. В SQL Server 2016 и базе данных SQL Azure операции ALTER TABLE с таблицами, оптимизированными для памяти, являются автономными, то есть во время выполнения такой операции таблица недоступна для запросов. Приложение базы данных может продолжать работу, и любая операция, которая обращается к таблице, будет блокироваться до завершения процесса изменения. В одной инструкции ALTER TABLE можно сочетать несколько операций ADD, DROP или ALTER.
  
## <a name="alter-table"></a>ALTER TABLE  
 
Синтаксис инструкции ALTER TABLE используется для внесения изменений в схему таблицы, а также для добавления, удаления и перестроения индексов. Индексы являются частью определения таблицы:  
  
-   Синтаксис инструкции ALTER TABLE ADD/DROP/ALTER INDEX поддерживается только для таблиц, оптимизированных для памяти.  
  
-   Без использования инструкции ALTER TABLE инструкции CREATE INDEX, DROP INDEX и ALTER INDEX *не* поддерживаются для индексов в таблицах, оптимизированных для памяти.  
  
Поддерживаются следующие типы изменений:  
  
-   Изменение числа контейнеров  
  
-   Добавление и удаление индекса  
  
-   Изменение, добавление и удаление столбца  
  
-   Добавление и удаление ограничения  
  
 Дополнительные сведения о функции ALTER TABLE и полный синтаксис см. в статье [ALTER TABLE (Transact-SQL)](../../t-sql/statements/alter-table-transact-sql.md).  
  
## <a name="schema-bound-dependency"></a>Зависимость, привязанная к схеме  
 Скомпилированные в собственном коде хранимые процедуры должны быть привязаны к схеме, а значит иметь привязанную к схеме зависимость от оптимизированных в памяти таблиц, к которым они обращаются, и столбцов, на которые они ссылаются. Привязанная к схеме зависимость — это связь между двумя сущностями, которая не допускает удаления или несовместимого изменения упоминаемой сущности, пока существует ссылающаяся сущность.  
  
 Например, если скомпилированная в собственном коде и привязанная к схеме хранимая процедура ссылается на столбец *c1* из таблицы *mytable*, столбец *c1* удалить нельзя. Точно так же при наличии процедуры с инструкцией INSERT без списка столбцов (например, `INSERT INTO dbo.mytable VALUES (...)`), ни один из столбцов в таблице удалить нельзя.  
 
## <a name="logging-of-alter-table-on-memory-optimized-tables"></a>Ведение журнала ALTER TABLE для таблиц, оптимизированных для памяти
В таблицах, оптимизированных для памяти, большинство сценариев ALTER TABLE теперь выполняются параллельно и позволяют оптимизировать операции записи в журнал транзакций. Оптимизация заключается в том, что только изменения метаданных записываются в журнал транзакций. Тем не менее следующие операции ALTER TABLE запускаются в одном потоке и не оптимизированы для журнала.

В этом случае однопотоковая операция записала бы в журнал транзакций все содержимое измененной таблицы. Далее приведен список операций, выполняемых в одном потоке:

- изменение и добавление столбца для использования типа данных больших объектов (LOB): nvarchar(max), varbinary(max) или varchar(max);

- добавление или удаление индекса columnstore;

- практически все, что влияет на [столбец вне строки](../../relational-databases/in-memory-oltp/supported-data-types-for-in-memory-oltp.md);

    - перемещение столбца в строке за пределы строки;

    - перемещение столбца вне строки в строку;

    - создание нового столбца вне строки.

    - *Исключение:* удлинение столбца, который уже находится вне строки, фиксируется в журнале оптимизированным образом. 
  
## <a name="examples"></a>Примеры  
 В следующем примере изменяется число контейнеров существующего хэш-индекса. Это приводит к перестроению хэш-индекса с помощью нового числа контейнеров, при этом другие свойства хэш-индекса остаются неизменными.  
  
```sql
ALTER TABLE Sales.SalesOrderDetail_inmem   
       ALTER INDEX imPK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID  
              REBUILD WITH (BUCKET_COUNT=67108864);  
GO
```
  
 В следующем примере добавляется столбец с ограничением NOT NULL и с определением DEFAULT и использует аргумент WITH VALUES для предоставления значений каждой существующей строке таблицы. Если аргумент WITH VALUES не используется, то каждая строка в новом столбце имеет значение NULL.  
  
```sql  
ALTER TABLE Sales.SalesOrderDetail_inmem  
       ADD Comment NVARCHAR(100) NOT NULL DEFAULT N'' WITH VALUES;  
GO
```  
  
 В следующем примере к существующему столбцу добавляется ограничение первичного ключа.  
  
```sql
CREATE TABLE dbo.UserSession (   
   SessionId int not null,   
   UserId int not null,   
   CreatedDate datetime2 not null,   
   ShoppingCartId int,   
   index ix_UserId nonclustered hash (UserId) with (bucket_count=400000)   
)   
WITH (MEMORY_OPTIMIZED=ON, DURABILITY=SCHEMA_ONLY) ;  
GO  
  
ALTER TABLE dbo.UserSession  
       ADD CONSTRAINT PK_UserSession PRIMARY KEY NONCLUSTERED (SessionId);  
GO
```  
  
 В следующем примере удаляется индекс.  
  
```sql
ALTER TABLE Sales.SalesOrderDetail_inmem  
       DROP INDEX ix_ModifiedDate;  
GO
```  
  
 В следующем примере добавляется индекс.  
  
```sql  
ALTER TABLE Sales.SalesOrderDetail_inmem  
       ADD INDEX ix_ModifiedDate (ModifiedDate);  
GO  
```  
  
 В следующем примере добавляется несколько столбцов с индексом и ограничениями.  
  
```sql
ALTER TABLE Sales.SalesOrderDetail_inmem  
       ADD    CustomerID int NOT NULL DEFAULT -1 WITH VALUES,  
              ShipMethodID int NOT NULL DEFAULT -1 WITH VALUES,  
              INDEX ix_Customer (CustomerID);  
GO  
```


<a name="logging-of-alter-table-on-memory-optimized-tables-124"></a>


## <a name="see-also"></a>См. также:  

[Таблицы, оптимизированные для памяти](../../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  

