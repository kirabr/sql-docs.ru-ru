---
title: Столбцы данных событий уведомлений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Notification Events event category
ms.assetid: 0ecf06da-1586-415a-9da8-60d4c634f030
caps.latest.revision: 29
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 6a436f613b39f5beb18a7dea40349ce24ded1bf5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37204074"
---
# <a name="notification-events-data-columns"></a>Столбцы данных событий уведомлений
  События уведомлений — это события, не вызванные непосредственно пользователями служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Например, уведомления происходят при обновлении пользователями базовых таблиц для упреждающего кэширования.  
  
 В категории событий «События уведомления» есть следующие классы событий:  
  
|**Идентификатор события**|**Имя события**|**Описание события**|  
|------------------|--------------------|---------------------------|  
|39|Уведомление|Событие уведомления.|  
|40|Определяемые пользователем|Определяемое пользователем событие.|  
  
 В следующей таблице перечислены столбцы данных для класса событий.  
  
## <a name="notification"></a>Уведомление  
  
|**Имя столбца**|**Идентификатор столбца**|**Тип столбца**|**Описание столбца**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Класс событий используется для категоризации событий.|  
|EventSubclass|1|1|Подкласс событий предоставляет дополнительные сведения о каждом классе событий. Ниже приведены допустимые пары имен подкласс идентификатор/подкласс.<br /><br /> 0: начало упреждающего кэширования<br />1: окончание упреждающего кэширования<br />2: "черный ящик" запущен<br />3: "черный ящик" остановлен<br />4: свойства конфигурации обновлены<br />5: трассировка SQL<br />6: объект создан<br />7: объект удален<br />8: объект изменен<br />9: начало опроса упреждающего кэширования<br />10: окончание опроса упреждающего кэширования<br />11: начало моментального снимка "черного ящика"<br />12: окончание моментального снимка "черного ящика"<br />13: упреждающее кэширование — обновлен подлежащий уведомлению объект<br />14: отложенная обработка — начало обработки<br />15: отложенная обработка — завершение обработки<br />16: начало события SessionOpened<br />17: окончание события SessionOpened<br />18: начало события SessionClosing<br />19: окончание события SessionClosing<br />20: начало события CubeOpened<br />21: окончание события CubeOpened<br />22: начало события CubeClosing<br />23: окончание события CubeClosing<br />24: запрошено прерывание транзакции|  
|CurrentTime|2|5|Содержит текущее время события оповещения, если оно доступно. Ожидаемые форматы фильтрации: «ГГГГ-ММ-ДД» и «ГГГГ-ММ-ДД ЧЧ:ММ:СС».|  
|StartTime|3|5|Содержит время начала события, если оно доступно. Ожидаемые форматы фильтрации: «ГГГГ-ММ-ДД» и «ГГГГ-ММ-ДД ЧЧ:ММ:СС».|  
|EndTime|4|5|Содержит время окончания события. Этот столбец не заполняется для таких классов событий запуска, как SQL:BatchStarting или SP:Starting. Ожидаемые форматы фильтрации: «ГГГГ-ММ-ДД» и «ГГГГ-ММ-ДД ЧЧ:ММ:СС».|  
|Duration|5|2|Содержит время в миллисекундах, использованное событием.|  
|IntegerData|10|1|Содержит целочисленные данные, связанные с событием уведомления. Если в столбце EventSubclass содержится 8, значения следующие:<br /><br /> 1 = создано<br /><br /> 2 = удалено<br /><br /> 3 = изменены свойства объекта<br /><br /> 4 = изменены свойства потомков объекта<br /><br /> 6 = добавлены потомки<br /><br /> 7 = удалены потомки<br /><br /> 8 = объект полностью обработан<br /><br /> 9 = объект частично обработан<br /><br /> 10 = объект не обработан<br /><br /> 11 = объект полностью оптимизирован<br /><br /> 12 = объект частично оптимизирован<br /><br /> 13 = объект не оптимизирован|  
|ObjectID|11|8|Содержит идентификатор объекта, для которого выдано данное уведомление; это строковое значение.|  
|ObjectType|12|1|Содержит тип объекта, связанный с событием уведомления.|  
|ObjectName|13|8|Содержит имя объекта, связанное с событием уведомления.|  
|ObjectPath|14|8|Содержит путь объекта, связанный с событием уведомления. Путь возвращается в виде разделенного запятыми списка родителей, начиная с родителя объекта.|  
|ObjectReference|15|8|Содержит ссылку объекта для события завершения отчета о состоянии. Ссылка объекта кодируется всеми родителями в виде XML с использованием тегов для описания объекта.|  
|ConnectionID|25|1|Содержит уникальный идентификатор соединения, связанный с событием уведомления.|  
|DatabaseName|28|8|Содержит имя базы данных, в которой произошло событие уведомления.|  
|NTUserName|32|8|Содержит имя пользователя Windows, сопоставленное с событием уведомления.|  
|NTDomainName|33|8|Домен Windows, к которому принадлежит пользователь.|  
|SessionID|39|8|Содержит идентификатор сеанса, связанный с событием уведомления.|  
|NTCanonicalUserName|40|8|Содержит имя пользователя Windows, сопоставленное с событием уведомления. Имя пользователя указано в канонической форме. Например, engineering.microsoft.com/software/user.|  
|SPID|41|1|Содержит идентификатор серверного процесса (SPID), уникальным образом определяющий сеанс пользователя, связанный с событием уведомления. Идентификатор SPID напрямую соответствует идентификатору GUID сеанса, используемому XML для аналитики.|  
|TextData|42|9|Содержит текстовые данные, связанные с событием уведомления.|  
|ServerName|43|8|Содержит имя экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , в котором было создано уведомление.|  
|RequestProperties|45|9|Содержит свойства запроса XMLA.|  
  
## <a name="user-defined"></a>Определяемые пользователем  
  
|**Имя столбца**|**Идентификатор столбца**|**Тип столбца**|**Описание столбца**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|Класс событий используется для категоризации событий.|  
|EventSubclass|1|1|Определенный подкласс пользовательского события, предоставляющий дополнительные сведения о каждом классе событий.|  
|CurrentTime|2|5|Содержит текущее время события оповещения, если оно доступно. Ожидаемые форматы фильтрации: «ГГГГ-ММ-ДД» и «ГГГГ-ММ-ДД ЧЧ:ММ:СС».|  
|IntegerData|10|1|Сведения об определенном пользовательском событии.|  
|ConnectionID|25|1|Содержит уникальный идентификатор соединения, связанный с событием уведомления.|  
|DatabaseName|28|8|Содержит имя базы данных, в которой произошло событие уведомления.|  
|NTUserName|32|8|Содержит имя пользователя Windows, сопоставленное с событием уведомления.|  
|NTDomainName|33|8|Домен Windows, к которому принадлежит пользователь.|  
|SessionID|39|8|Содержит идентификатор сеанса, связанный с событием уведомления.|  
|NTCanonicalUserName|40|8|Содержит имя пользователя Windows, сопоставленное с событием уведомления. Имя пользователя указано в канонической форме. Например, engineering.microsoft.com/software/user.|  
|SPID|41|1|Содержит идентификатор серверного процесса (SPID), уникальным образом определяющий сеанс пользователя, связанный с событием уведомления. Идентификатор SPID напрямую соответствует идентификатору GUID сеанса, используемому XML для аналитики.|  
|TextData|42|9|Содержит текстовые данные, связанные с событием уведомления.|  
|ServerName|43|8|Содержит имя экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , в котором было создано уведомление.|  
  
## <a name="see-also"></a>См. также  
 [Категория событий «События уведомления»](notification-events-event-category.md)  
  
  
