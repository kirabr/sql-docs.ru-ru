---
title: Изменение шаблона трассировки (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- modifying traces
ms.assetid: b81df2a1-e202-43d8-92b0-0beb145f0116
caps.latest.revision: 25
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 8079f4dfa5893915a10ae044045d1cc9eb59baa8
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37299374"
---
# <a name="modify-a-trace-template-sql-server-profiler"></a>редактировать шаблон трассировки (приложение SQL Server Profiler)
  В этом подразделе описывается модификация шаблона трассировки с помощью [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].  
  
### <a name="to-modify-a-trace-template"></a>Изменение шаблона трассировки  
  
1.  В меню **Файл** выберите **Шаблоны**и затем выберите **Изменить шаблон**.  
  
2.  В диалоговом окне **Свойства шаблона трассировки** на вкладке **Общие** можно изменить тип сервера и имя шаблона или выбрать использование шаблона по умолчанию для типа сервера.  
  
3.  В меню **Выбор событий**используйте сетку для добавления или удаления событий и столбцов данных в файле трассировки следующим образом:  
  
    -   Чтобы добавить событие, разверните соответствующую категорию событий в столбце **События** и выберите имя события.  
  
    -   При добавлении события все относящиеся к нему столбцы данных включаются автоматически. Чтобы удалить столбец данных для события из трассировки, снимите флажок в столбце данных для этого события.  
  
    -   Чтобы добавить фильтры, щелкните имя столбца данных и определите критерии фильтра в диалоговом окне **Изменение фильтра** . Также можно щелкнуть имя столбца данных правой кнопкой мыши и выбрать пункт **Изменить фильтр столбца** , чтобы открыть диалоговое окно **Изменение фильтра** . Нажмите кнопку **ОК** , чтобы добавить фильтр.  
  
4.  Нажмите кнопку **Сохранить**или кнопку **Сохранить As**для сохранения шаблона трассировки под другим именем.  
  
## <a name="see-also"></a>См. также  
 [Указать столбцы событий и данных для файла трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)   
 [Извлечение шаблона из выполняемой трассировки (приложение SQL Server Profiler)](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md)   
 [Извлечение шаблона из файла трассировки или таблицы трассировки (приложение SQL Server Profiler)](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md)   
 [Шаблоны и разрешения приложения SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md)   
 [Приложение SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
