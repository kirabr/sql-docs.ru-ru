---
title: Просмотр определяемых пользователем функций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.udfproperties.general.f1
- sql12.swb.functionproperties.general.f1
helpviewer_keywords:
- displaying user-defined functions
- viewing user-defined functions
- user-defined functions [SQL Server], viewing
- status information [SQL Server], user-defined functions
ms.assetid: a45dfab5-6384-4311-b935-2e23a70c5c10
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 69ad8efa0fcf4f5648695138f4cc4dfbaa98f255
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37425263"
---
# <a name="view-user-defined-functions"></a>Просмотр определяемых пользователем функций
  Получить сведения об определении или свойствах определяемой пользователем функции в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)]. Возможность просмотреть определение функции может понадобиться, чтобы понять, как его данные извлекаются из исходных таблиц, или чтобы увидеть данные, определенные функцией.  
  
> [!IMPORTANT]  
>  Если имя объекта, на который ссылается функция, было изменено, необходимо изменить функцию так, чтобы в ее тексте использовалось новое имя. Поэтому, прежде чем переименовать объект, отобразите список его зависимостей, чтобы определить, отразится ли планируемое изменение на каких-либо функциях.  
  
 **В этом разделе**  
  
-   **Перед началом работы**  
  
     [безопасность](#Security)  
  
-   **Для получения сведений о функции используется:**  
  
     [Среда SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Перед началом  
  
###  <a name="Security"></a> безопасность  
  
####  <a name="Permissions"></a> Permissions  
 Для использования **sys.sql_expression_dependencies** в поиске всех зависимостей функции необходимо разрешение VIEW DEFINITION на базу данных и разрешение SELECT на представление **sys.sql_expression_dependencies** для базы данных. Определения системных объектов, например полученные в OBJECT_DEFINITION, видимы для всех.  
  
##  <a name="SSMSProcedure"></a> Использование среды SQL Server Management Studio  
  
#### <a name="to-show-a-user-defined-functions-properties"></a>Отображение свойств определяемой пользователем функции  
  
1.  В **обозревателе объектов**щелкните знак «плюс» рядом с базой данных, содержащей функцию, свойства которой необходимо просмотреть, а затем щелкните знак «плюс», чтобы развернуть папку **Программирование** .  
  
2.  Чтобы развернуть папку **Функции** , щелкните знак «плюс» (+).  
  
3.  Щелкните знак «плюс», чтобы развернуть папку, содержащую функцию, для которой нужно просмотреть свойства.  
  
    -   Table-valued Function  
  
    -   Скалярная функция  
  
    -   Агрегатная функция  
  
4.  Щелкните правой кнопкой мыши функцию, свойства которой необходимо просмотреть, и выберите пункт **Свойства**.  
  
     Следующие свойства отображаются в диалоговом окне **Свойства функции —***имя_функции*.  
  
     **База данных**  
     Имя базы данных, содержащей эту функцию.  
  
     **Server**  
     Имя текущего экземпляра сервера.  
  
     **Пользователь**  
     Имя пользователя этого соединения.  
  
     **Дата создания**  
     Дата создания функции.  
  
     **Выполнить от имени**  
     Контекст выполнения для функции.  
  
     **Название**  
     Имя текущей функции.  
  
     **Схема**  
     Схема, которой принадлежит функция.  
  
     **Системный объект**  
     Указывает принадлежность функции к системным объектам. Возможные значения: True и False.  
  
     **Значения NULL по стандарту ANSI**  
     Указывает, был ли объект создан с параметром ANSI NULL.  
  
     **Зашифрована**  
     Указывает, зашифрована ли функция. Возможные значения: True и False.  
  
     **Тип функции**  
     Тип определяемой пользователем функции.  
  
     **Заключенный в кавычки идентификатор**  
     Показывает, был ли объект создан с параметром «заключенный в кавычки идентификатор».  
  
     **Привязка к схеме**  
     Указывает, привязана ли функция к схеме. Возможные значения: True и False. Дополнительные сведения о функциях, привязанных к схеме, см. в подразделе SCHEMABINDING раздела [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql).  
  
##  <a name="TsqlProcedure"></a> Использование Transact-SQL  
  
#### <a name="to-get-the-definition-and-properties-of-a-function"></a>Получение определения и свойств функции  
  
1.  В **обозревателе объектов** подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].  
  
2.  На стандартной панели выберите пункт **Создать запрос**.  
  
3.  Скопируйте и вставьте один из следующих примеров в окно запроса и нажмите кнопку **Выполнить**.  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the function name, definition, and relevant properties  
    SELECT sm.object_id,   
       OBJECT_NAME(sm.object_id) AS object_name,   
       o.type,   
       o.type_desc,   
       sm.definition,  
       sm.uses_ansi_nulls,  
       sm.uses_quoted_identifier,  
       sm.is_schema_bound,  
       sm.execute_as_principal_id  
    -- using the two system tables sys.sql_modules and sys.objects  
    FROM sys.sql_modules AS sm  
    JOIN sys.objects AS o ON sm.object_id = o.object_id  
    -- from the function 'dbo.ufnGetProductDealerPrice'  
    WHERE sm.object_id = OBJECT_ID('dbo.ufnGetProductDealerPrice')  
    ORDER BY o.type;  
    GO  
  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the definition of the function dbo.ufnGetProductDealerPrice  
    SELECT OBJECT_DEFINITION (OBJECT_ID('dbo.ufnGetProductDealerPrice')) AS ObjectDefinition;  
    GO  
    ```  
  
 Дополнительные сведения см. в разделах [sys.sql_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) и [OBJECT_DEFINITION (Transact-SQL)](/sql/t-sql/functions/object-definition-transact-sql).  
  
#### <a name="to-get-the-dependencies-of-a-function"></a>Получение зависимостей функции  
  
1.  В **обозревателе объектов** подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].  
  
2.  На стандартной панели выберите пункт **Создать запрос**.  
  
3.  Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get all of the dependency information  
    SELECT OBJECT_NAME(sed.referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(sed.referencing_id, sed.referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        sed.referencing_class_desc, sed.referenced_class_desc,  
        sed.referenced_server_name, sed.referenced_database_name, sed.referenced_schema_name,  
        sed.referenced_entity_name,   
        COALESCE(COL_NAME(sed.referenced_id, sed.referenced_minor_id), '(n/a)') AS referenced_column_name,  
        sed.is_caller_dependent, sed.is_ambiguous  
    -- from the two system tables sys.sql_expression_dependencies and sys.object  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    -- on the function dbo.ufnGetProductDealerPrice  
    WHERE sed.referencing_id = OBJECT_ID('dbo.ufnGetProductDealerPrice');  
    GO  
    ```  
  
 Дополнительные сведения см. в разделах [sys.sql_expression_dependencies (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) и [sys.objects (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).  
  
  
