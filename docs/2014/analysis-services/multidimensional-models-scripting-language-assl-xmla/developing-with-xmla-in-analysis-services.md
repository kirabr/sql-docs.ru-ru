---
title: Разработка с использованием XMLA в службах Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- XML for Analysis, data mining
- commands [XML for Analysis]
- data mining [XML for Analysis]
- XMLA, data mining
- XML for Analysis, Analysis Services tasks
- XMLA, Analysis Services tasks
ms.assetid: 54445ee7-720c-4683-99a6-e75b3dcca904
caps.latest.revision: 31
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: f4eef38459df5d2d872646a7bc64973028d25ac4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37265660"
---
# <a name="developing-with-xmla-in-analysis-services"></a>Разработка с использованием XMLA в службах Analysis Services
  XML для аналитики (XMLA) — это XML-протокол, основанный на протоколе SOAP и специально предназначенный для обеспечения унифицированного доступа к данным в любом стандартном многомерном источнике данных, доступном через HTTP-соединение. В службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA является единственным протоколом для связи с клиентскими приложениями. Все клиентские библиотеки, поддерживаемые службами Analysis Services, в конечном итоге формируют запросы и ответы по протоколу XMLA.  
  
 С помощью XMLA разработчик может интегрировать клиентское приложение со службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], не создавая зависимости от платформы .NET Framework и COM-интерфейсов. Требования приложений, в том числе касающиеся размещения на широком диапазоне платформ, можно выполнить с помощью XMLA и HTTP-соединения со службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
 Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] полностью соответствуют спецификации XMLA 1.1 и расширяют ее для поддержки описания данных, обработки данных и управления данными. Расширения служб Analysis Services называются языком ASSL. Совместное использование XMLA и ASSL расширяет набор возможностей XMLA. Дополнительные сведения о ASSL см. в разделе [разработка с использованием язык сценариев служб Analysis Services &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).  
  
## <a name="in-this-section"></a>в этом разделе  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Управление соединениями и сеансами &#40;XML для Аналитики&#41;](managing-connections-and-sessions-xmla.md)|Описывает соединение с экземпляром служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и управление сеансами и поддержкой состояния в XML для аналитики.|  
|[Обработка ошибок и предупреждений &#40;XML для Аналитики&#41;](handling-errors-and-warnings-xmla.md)|Описывает, каким образом службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] возвращают сведения об ошибках и предупреждениях для методов и команд XML для аналитики.|  
|[Определение и идентификация объектов &#40;XML для Аналитики&#41;](../xmla/xml-elements-objects.md)|Описывает идентификаторы и ссылки объектов, а также их использование в командах XML для аналитики.|  
|[Управление транзакциями &#40;XML для Аналитики&#41;](managing-transactions-xmla.md)|Подробное описание использования [BeginTransaction](../xmla/xml-elements-commands/begintransaction-element-xmla.md), [CommitTransaction](../xmla/xml-elements-commands/committransaction-element-xmla.md), и [RollbackTransaction](../xmla/xml-elements-commands/rollbacktransaction-element-xmla.md) команды, чтобы явным образом определять и управлять ими транзакцию в текущем XML для Аналитики сеанс.|  
|[Отмена команд &#40;XML для Аналитики&#41;](../multidimensional-models-scripting-language-assl-xmla/canceling-commands-xmla.md)|Описывает использование [отменить](../xmla/xml-elements-commands/cancel-element-xmla.md)команду для отмены команд, сеансов и соединений в XML для Аналитики.|  
|[Выполнение пакетных операций &#40;XML для Аналитики&#41;](performing-batch-operations-xmla.md)|Описывает использование [пакета](../xmla/xml-elements-commands/batch-element-xmla.md) команду для запуска нескольких XML для Аналитики команды, последовательно или параллельно, как в той же транзакции, так и отдельные транзакции, при помощи только одного [Execute](../xmla/xml-elements-methods-execute.md) метод.|  
|[Создание и изменение объектов &#40;XML для Аналитики&#41;](creating-and-altering-objects-xmla.md)|Описывает использование [создать](../xmla/xml-elements-commands/create-element-xmla.md), [Alter](../xmla/xml-elements-commands/alter-element-xmla.md), и [удалить](../xmla/xml-elements-commands/delete-element-xmla.md) команды, а также элементы языка сценариев служб Analysis Services (ASSL) для определения, изменения или удаления объекты из [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] экземпляра.|  
|[Блокировка и снятие блокировки баз данных &#40;XML для Аналитики&#41;](locking-and-unlocking-databases-xmla.md)|Подробное описание использования [блокировки](../xmla/xml-elements-commands/lock-element-xmla.md) и [Unlock](../xmla/xml-elements-commands/unlock-element-xmla.md) команды, чтобы блокировать и разблокировать [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базы данных.|  
|[Обработка объектов &#40;XML для Аналитики&#41;](processing-objects-xmla.md)|Описывает использование [процесс](../xmla/xml-elements-commands/process-element-xmla.md) команду к процессу [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] объекта.|  
|[Слияние секций &#40;XML для Аналитики&#41;](merging-partitions-xmla.md)|Описывает использование [MergePartitions](../xmla/xml-elements-commands/mergepartitions-element-xmla.md) команды для слияния секций в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] экземпляра.|  
|[Проектирование агрегатов &#40;XML для Аналитики&#41;](designing-aggregations-xmla.md)|Описывает использование [DesignAggregations](../xmla/xml-elements-commands/designaggregations-element-xmla.md) команды, в последовательном или пакетном режиме для проектирования агрегатов для статистических схем в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].|  
|[Резервное копирование, восстановление и синхронизация баз данных &#40;XML для Аналитики&#41;](backing-up-restoring-and-synchronizing-databases-xmla.md)|Описывает использование [резервного копирования](../xmla/xml-elements-commands/backup-element-xmla.md) и [восстановить](../xmla/xml-elements-commands/restore-element-xmla.md) команды для резервного копирования и восстановления [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базы данных из файла резервной копии.<br /><br /> Также описывается использование [Synchronize](../xmla/xml-elements-commands/synchronize-element-xmla.md) команду, чтобы синхронизировать [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базы данных с помощью существующей базы данных в одном экземпляре или на другом экземпляре.|  
|[Вставка, обновление и удаление элементов &#40;XML для Аналитики&#41;](inserting-updating-and-dropping-members-xmla.md)|Описывает использование [вставить](../xmla/xml-elements-commands/insert-element-xmla.md), [обновление](../xmla/xml-elements-commands/update-element-xmla.md), и [Drop](../xmla/xml-elements-commands/drop-element-xmla.md) команды, чтобы добавить, изменить или удалить элементы из измерения, доступного для записи.|  
|[Обновление ячеек &#40;XML для Аналитики&#41;](updating-cells-xmla.md)|Описывает использование [UpdateCells](../xmla/xml-elements-commands/updatecells-element-xmla.md) команду, чтобы изменить значения ячеек в секции, доступные для записи.|  
|[Управление кэшами &#40;XML для Аналитики&#41;](managing-caches-xmla.md)|Подробное описание использования [ClearCache](../xmla/xml-elements-commands/clearcache-element-xmla.md) команду, чтобы очистить кэш [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] объектов.|  
|[Наблюдение за трассировками &#40;XML для Аналитики&#41;](monitoring-traces-xmla.md)|Описывает использование [Subscribe](../xmla/xml-elements-commands/subscribe-element-xmla.md) команду, чтобы подписаться на и наблюдения за существующей трассировки на [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] экземпляра.|  
  
## <a name="data-mining-with-xmla"></a>Интеллектуальный анализ данных в XML для аналитики  
 Протокол XML для аналитики полностью поддерживает наборы строк схемы интеллектуального анализа данных. Эти наборы строк содержат сведения для выполнения запросов к модели интеллектуального анализа данных с использованием [Discover](../xmla/xml-elements-methods-discover.md) метод. Дополнительные сведения о наборах строк схемы интеллектуального анализа данных см. в разделе [наборы строк схемы интеллектуального анализа данных](../schema-rowsets/data-mining/data-mining-schema-rowsets.md) 
  
 Дополнительные сведения о расширениях интеллектуального анализа данных, см. в разделе [расширения интеллектуального анализа данных &#40;расширений интеллектуального анализа данных&#41; ссылку](/sql/dmx/data-mining-extensions-dmx-reference).  
  
## <a name="namespace-and-schema"></a>Пространство имен и схема  
  
### <a name="namespace"></a>Пространство имен  
 Схемы, определенной в данной спецификации использует пространство имен XML http://schemas.microsoft.com/AnalysisServices/2003/Engine и стандартное сокращение «DDL».  
  
### <a name="schema"></a>Схема  
 В основе определения схемы XSD для языка определения объектов служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] лежат определение элементов схемы и иерархии, приведенное в этом разделе.  
  
## <a name="extensibility"></a>Расширяемость  
 Расширяемость схемы языка определения объектов обеспечивается за счет элемента `Annotation`, который включается во все объекты. Этот элемент может содержать любой допустимый код XML из любого пространства имен XML (отличного от целевого пространства имен, определяющего DDL) с соблюдением следующих правил.  
  
-   В XML-коде могут содержаться только элементы.  
  
-   Каждый элемент должен иметь уникальное имя. Рекомендуется, чтобы значение `Name` ссылалось на целевое пространство имен.  
  
 Эти правила налагаются с тем, чтобы можно было предоставлять доступ к содержимому тега `Annotation`, как к набору пар «Имя/Значение», через объекты DSO 9.0.  
  
 Если комментарии и пробелы в теге `Annotation` не были заключены в дочерний элемент, то они могут не сохраниться. Кроме того, все элементы должны быть доступными для чтения и записи; элементы, доступные только для чтения, пропускаются.  
  
 Схема языка определения объектов является закрытой; под этим подразумевается то, что сервер не позволяет производить замену производных типов для элементов, определенных в схеме. Поэтому сервер принимает только набор элементов, определенных в схеме, и не принимает другие элементы или атрибуты. Обнаружение неизвестного элемента вынуждает ядро служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] активизировать ошибку.  
  
## <a name="see-also"></a>См. также  
 [Язык сценариев разработки с использованием Analysis Services &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)   
 [Основные сведения об архитектуре Microsoft OLAP](../multidimensional-models/olap-physical/understanding-microsoft-olap-architecture.md)  
  
  
