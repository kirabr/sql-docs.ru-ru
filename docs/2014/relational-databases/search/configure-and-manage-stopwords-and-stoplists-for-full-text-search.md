---
title: Настройка стоп-слов и списков стоп-слов для полнотекстового поиска и управление ими | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: search
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- stoplists [full-text search]
- full-text search [SQL Server], stoplists
- full-text search [SQL Server], noise words
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 43b5ce7b-9f09-4443-8a5b-c3da6eb28bcc
caps.latest.revision: 79
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: c3ea419224478d1c4c45117795fe5a67ebfcaf5e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37284840"
---
# <a name="configure-and-manage-stopwords-and-stoplists-for-full-text-search"></a>Настройка и управление стоп-словами и списками стоп-слов для полнотекстового поиска
  Чтобы предотвратить чрезмерное увеличение полнотекстового индекса, в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] реализован механизм, отбрасывающий часто встречающиеся строки, не повышающие эффективность поиска. Эти отброшенные строки называются *стоп-словами*. Во время создания индекса средство полнотекстового поиска не включает стоп-слова в полнотекстовый индекс. Это значит, что полнотекстовые запросы не будут выполнять поиск по стоп-словам.  
  
##  <a name="understand"></a> Основные сведения о стоп-слов и списков стоп-слов  
 Стоп-слово может быть словом конкретного языка или *токеном* , не имеющим лингвистического значения. Например, в английском языке такие слова, как «a», «and», «is» и «the», не включаются в полнотекстовый индекс, потому что при поиске они бесполезны.  
  
 Хотя стоп-слова при поиске не учитываются, полнотекстовый индекс принимает во внимание расположение таких слов. Рассмотрим для примера фразу «Instructions are applicable to these Adventure Works Cycles models». Позиции слов в этой фразе приведены в следующей таблице.  
  
|Word|Положение|  
|----------|--------------|  
|Instructions|1|  
|are|2|  
|applicable|3|  
|в|4|  
|these|5|  
|Adventure|6|  
|Works|7|  
|Cycles|8|  
|модели|9|  
  
 Стоп-слова «are», «to» и «these», занимающие позиции 2, 4 и 5, в полнотекстовый индекс не включаются. Однако данные об их позициях сохраняются, благодаря чему позиции других слов в фразе остаются неизменными.  
  
 Управление стоп-словами в базе данных производится через объекты, называемые списками стоп-слов. *Список стоп-слов* связан с полнотекстовым индексом и применяется к полнотекстовым запросам по этому индексу.  
  
  
##  <a name="creating"></a> Создание списка стоп-слов  
 Списки стоп-слов можно создать любым из следующих способов.  
  
-   Использование поддерживаемого системой списка стоп-слов в базе данных. В составе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставляется системный список стоп-слов, который содержит наиболее часто используемые стоп-слова для каждого поддерживаемого языка, то есть для любого языка, связанного по умолчанию с предложенными конкретными средствами разбиения по словам. Системный список стоп-слов содержит общие стоп-слова для всех поддерживаемых языков.  Можно скопировать системный список стоп-слов и внести необходимые изменения в созданную копию, добавляя и удаляя стоп-слова.  
  
     Системный список стоп-слов содержится в базе данных [Resource](../databases/resource-database.md) .  
  
-   Создание собственного списка стоп-слов, а затем добавление к нему стоп-слов, относящихся к любому заданному языку. При необходимости можно удалять стоп-слова из этого списка.  
  
-   Использование существующего пользовательского списка стоп-слов из другой базы данных в текущем экземпляре сервера и затем (при необходимости) добавление и удаление стоп-слов.  
  
 **Чтобы создать список стоп-слов**  
  
-   [CREATE FULLTEXT STOPLIST (Transact-SQL)](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql)  
  
#### <a name="to-create-a-full-text-stoplist-in-management-studio"></a>Для создания полнотекстового списка стоп-слов в Management Studio  
  
1.  В обозревателе объектов разверните узел сервера.  
  
2.  Разверните узел **Базы данных**, а затем разверните базу данных, в которой нужно создать список полнотекстовых стоп-слов.  
  
3.  Разверните узел **Хранилище**, а затем щелкните правой кнопкой мыши узел **Полнотекстовые списки стоп-слов**.  
  
4.  Выберите пункт **Создание полнотекстового списка стоп-слов**.  
  
5.  Укажите имя списка стоп-слов.  
  
6.  Дополнительно можно указать владельца списка стоп-слов.  
  
7.  Выберите один из следующих вариантов создания списка стоп-слов.  
  
    -   **Создать пустой список стоп-слов**  
  
    -   **Создать из системного списка стоп-слов**  
  
    -   **Создать из существующего полнотекстового списка стоп-слов**  
  
     Дополнительные сведения см. в разделе [Создание списка полнотекстовых стоп-слов (страница "Общие")](../../integration-services/general-page-of-integration-services-designers-options.md).  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 **Чтобы удалить список стоп-слов**  
  
-   [DROP FULLTEXT STOPLIST (Transact-SQL)](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
##  <a name="queries"></a> Использование списка стоп-слов в запросах полнотекстового поиска  
 Чтобы использовать список стоп-слов в запросах, нужно связать его с полнотекстовым индексом. Можно добавить список стоп-слов к полнотекстовому индексу при создании индекса или изменить индекс позже, добавив список стоп-слов.  
  
 **Для создания полнотекстового индекса и свяжите с ним список стоп-слов**  
  
-   [CREATE FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
 **Связывание или разъединение списка стоп-слов с помощью существующего полнотекстового индекса**  
  
-   [ALTER FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
 **Чтобы подавить сообщение об ошибке при неуспешном завершении логической операции, завершению запроса полнотекстового поиска**  
  
-   [Параметр конфигурации сервера «transform noise words»](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md)  
  
  
##  <a name="viewing"></a> Просмотр списков стоп-слов и метаданные списка стоп-слов  
 **Для просмотра всех стоп-слов из списка стоп-слов**  
  
-   [sys.fulltext_stopwords (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 **Для получения сведений о всех списков стоп-слов текущей базы данных**  
  
-   [sys.fulltext_stoplists (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
-   [sys.fulltext_stopwords (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 **Просмотр итогового результата разметки сочетания средства разбиения по словам, тезауруса и списка стоп-слов word**  
  
-   [sys.dm_fts_parser (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="change"></a> Изменение стоп-слов в список стоп-слов  
 **Добавление или удаление стоп-слов из списка стоп-слов**  
  
-   [ALTER FULLTEXT STOPLIST (Transact-SQL)](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql)  
  
#### <a name="to-change-the-stopwords-in-a-stoplist-in-management-studio"></a>Изменение стоп-слов в списке стоп-слов в Management Studio  
  
1.  В обозревателе объектов разверните узел сервера.  
  
2.  Раскройте узел **Базы данных**, а затем — соответствующую базу данных.  
  
3.  Разверните узел **Хранилище**и выберите **Полнотекстовые списки стоп-слов**.  
  
4.  Щелкните правой кнопкой мыши список стоп-слов, свойства которого необходимо изменить, и выберите пункт **Свойства**.  
  
5.  В диалоговом окне [Свойства полнотекстового списка стоп-слов](../../database-engine/full-text-stoplist-properties.md) выполните указанные ниже действия.  
  
    1.  В списке **Действия** выберите одно из следующих действий: **Добавить стоп-слово**, **Удалить стоп-слово**, **Удалить все стоп-слова**или **Очистить список стоп-слов**.  
  
    2.  Если для выбранного действия доступно текстовое поле **Стоп-слово** , введите одно стоп-слово. Это стоп-слово должно быть уникальным; иными словами, оно еще не должно присутствовать в списке стоп-слов для выбранного языка.  
  
    3.  Если для выбранного действия доступен список **Язык полнотекстового поиска** , выберите язык.  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
##  <a name="upgrade"></a> Обновление пропускаемых слов из SQL Server 2005  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] пропускаемые слова были заменены стоп-словами. При обновлении базы данных с версии [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]файлы пропускаемых слов более не используются. Однако файлы пропускаемых слов хранятся в папке FTDATA\FTNoiseThresaurusBak, и их можно использовать в дальнейшем при обновлении или построении соответствующих списков стоп-слов. Сведения об обновлении файлов пропускаемых слов с переходом к спискам стоп-слов см. в разделе [Обновление полнотекстового поиска](upgrade-full-text-search.md).  
  
  
  
