---
title: Указание значений по умолчанию для столбцов | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: table-view-index, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: table-view-index
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], defaults
- default values
ms.assetid: 64514aed-b846-407b-992e-cf813f9a1a91
caps.latest.revision: 18
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 6d20700c29979d2fdefd79acb5e017258d497861
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "43070617"
---
# <a name="specify-default-values-for-columns"></a>Указание значений по умолчанию для столбца
[!INCLUDE[tsql-appliesto-ss2016-all-md](../../includes/tsql-appliesto-ss2016-all-md.md)]

  Можно указать значение по умолчанию, которое будет введено в столбец в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)]. Если значение по умолчанию не задано и пользователь оставляет столбец пустым, происходит следующее:  
  
-   если активирована поддержка значений NULL, в столбец вставляется значение NULL;  
  
-   если поддержка значений NULL не активирована, столбец остается пустым, но пользователь не сможет сохранить строку, пока не предоставит какое-либо значение.  
  
 **В этом разделе**  
  
-   **Перед началом работы**  
  
     [Ограничения](#Restrictions)  
  
     [безопасность](#Security)  
  
-   **Задание значения по умолчанию с использованием:**  
  
     [Среда SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Перед началом  
  
###  <a name="Restrictions"></a> Ограничения  
  
-   Если данные, введенные в поле **Значение по умолчанию** , заменяют связанное со столбцом значение по умолчанию (которое отображается без скобок), то будет предложено отменить привязку значения по умолчанию и заменить его новым значением.  
  
-   При вводе текстовых строк заключайте их в одинарные кавычки ('); не используйте двойные кавычки ("), потому что они зарезервированы для идентификаторов.  
  
-   Чтобы задать численное значение по умолчанию, введите число без одинарных кавычек.  
  
-   Чтобы задать объект или функцию, введите имя объекта или функции без двойных кавычек.  
  
###  <a name="Security"></a> безопасность  
  
####  <a name="Permissions"></a> Permissions  
 Требуется разрешение ALTER на таблицу.  
  
##  <a name="SSMSProcedure"></a> Использование среды SQL Server Management Studio  
  
#### <a name="to-specify-a-default-value-for-a-column"></a>Указание для столбца значения по умолчанию  
  
1.  В **Обозревателе объектов**щелкните правой кнопкой мыши таблицу со столбцами, масштаб которых необходимо изменить, и выберите пункт **Конструктор**.  
  
2.  Выберите столбец, для которого нужно задать значение по умолчанию.  
  
3.  На вкладке **Свойства столбца** введите новое значение по умолчанию в свойстве **Значение по умолчанию или привязка** .  
  
    > [!NOTE]  
    >  Чтобы задать численное значение по умолчанию, введите число. В случае объекта или функции нужно ввести его или ее имя. Чтобы задать алфавитно-цифровое значение по умолчанию, введите его, заключив в одинарные кавычки.  
  
4.  В меню **Файл** выберите пункт **Сохранить***имя_таблицы*.  
  
##  <a name="TsqlProcedure"></a> Использование Transact-SQL  
  
#### <a name="to-specify-a-default-value-for-a-column"></a>Указание для столбца значения по умолчанию  
  
1.  В **обозревателе объектов** подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  На стандартной панели выберите пункт **Создать запрос**.  
  
3.  Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.  
  
    ```  
    CREATE TABLE dbo.doc_exz ( column_a INT, column_b INT) ;  
    GO  
    INSERT INTO dbo.doc_exz (column_a)VALUES ( 7 ) ;  
    GO  
    ALTER TABLE dbo.doc_exz  
    ADD CONSTRAINT col_b_def  
    DEFAULT 50 FOR column_b ;  
    GO  
  
    ```  
  
 Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](../../t-sql/statements/alter-table-transact-sql.md).  
  
###  <a name="TsqlExample"></a>  
