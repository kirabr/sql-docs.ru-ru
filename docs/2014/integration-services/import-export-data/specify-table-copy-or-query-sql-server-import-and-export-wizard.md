---
title: Выбор копирования таблицы или запроса (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.specifytablecopyorquery.f1
ms.assetid: 08aa7158-40e6-4ef3-84d3-1265a8ba194c
caps.latest.revision: 43
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 44d7dfcb5928d0984c0ce34b314fd4d25adcc812
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37264950"
---
# <a name="specify-table-copy-or-query-sql-server-import-and-export-wizard"></a>Выбор копирования таблицы или запроса (мастер импорта и экспорта SQL Server)
  Используйте **Выбор копирования таблицы или запроса** страницу, чтобы указать способ копирования данных. Можно при помощи графического интерфейса выбрать существующие объекты базы данных или при помощи языка Transact-SQL создать более сложный запрос.  
  
 Дополнительные сведения о работе этого мастера см. в разделе [SQL Server Импорт и экспорт](import-and-export-data-with-the-sql-server-import-and-export-wizard.md). Дополнительные сведения о режимах запуска мастера, а также разрешения, необходимые для успешного запуска мастера, см. в разделе [запустить мастер экспорта и импорта SQL Server](start-the-sql-server-import-and-export-wizard.md).  
  
 Назначение мастера импорта и экспорта SQL Server заключается в копировании данных из исходного расположения в целевое. Этот мастер может также создать целевую базу данных и целевые таблицы. Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных. Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).  
  
## <a name="options"></a>Параметры  
 **Скопировать данные из одной или нескольких таблиц или представлений**  
 Копировать поля из выбранных исходных таблиц и представлений в нужное место или места назначения с помощью **Выбор исходных таблиц и представлений** диалоговое окно. Используйте этот режим, если нужно копировать все данные из источника без фильтрации или упорядочения записей.  
  
 При использовании [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] поставщик данных для подключения к источнику данных, **копирование данных из одного или нескольких таблиц или представлений** параметр может быть недоступен. Этот параметр доступен только для поставщиков, у которых имеется раздел ProviderDescription в файле ProviderDescriptors.xml. Каждый раздел ProviderDescription содержит сведения, необходимые для получения метаданных от соответствующего поставщика. По умолчанию файл ProviderDescriptors.xml содержит раздел ProviderDescription только для следующих поставщиков:  
  
-   System.Data.SqlClient  
  
-   System.Data.OracleClient  
  
-   System.Data.OleDb  
  
-   System.Data.Odbc  
  
 Чтобы сделать **копирование данных из одного или нескольких таблиц или представлений** доступны для дополнительных поставщиков, сторонние разработчики могут добавлять свои собственные разделы ProviderDescriptor файл ProviderDescriptors.xml. По умолчанию этот файл находится в \< *диск*>: \Program Files\Microsoft SQL Server\100\DTS\ProviderDescriptors. Требования к разделу ProviderDescriptor см. в файле схемы ProviderDescriptors.xsd, который по умолчанию расположен в той же папке, что и файл ProviderDescriptors.xml.  
  
 **Написать запрос, указывающий данные для передачи**  
 Инструкции SQL для получения строк при помощи **определение исходного запроса** диалоговое окно. Используйте этот режим, если при копировании нужно изменять или фильтровать исходные данные. Копироваться будут только строки, удовлетворяющие критерию отбора.  
  
  
