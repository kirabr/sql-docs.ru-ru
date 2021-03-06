---
title: Набор строк DMSCHEMA_MINING_MODEL_XML | Документы Microsoft
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: schema-rowsets
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: e4aa4451c8fed5ceec07609bbb0a22628bc35777
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
ms.locfileid: "34028245"
---
# <a name="dmschemaminingmodelxml-rowset"></a>Набор строк DMSCHEMA_MINING_MODEL_XML
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Возвращает XML-структуру модели интеллектуального анализа данных. Формат XML-строки соответствует стандарту языка разметки прогнозирующих моделей (PMML 2.1).  
  
## <a name="rowset-columns"></a>Столбцы наборов строк  
 Набор строк **DMSCHEMA_MINING_MODEL_XML** содержит следующие столбцы.  
  
|Имя столбца|Индикатор типа|Длина|Описание|  
|-----------------|--------------------|------------|-----------------|  
|**MODEL_CATALOG**|**DBTYPE_WSTR**||Имя каталога. Заполняется именем базы данных, элементом которой является модель.|  
|**MODEL_SCHEMA**|**DBTYPE_WSTR**||Неполное имя схемы. Этот столбец не поддерживается [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]; он всегда содержит **NULL**.|  
|**MODEL_NAME**|**DBTYPE_WSTR**||Имя модели. Этот столбец не может содержать значение **NULL**.|  
|**MODEL_TYPE**|**DBTYPE_WSTR**||Тип модели. Строка, зависящая от поставщика. Она может иметь значение **NULL**.|  
|**MODEL_GUID**|**DBTYPE_GUID**||Идентификатор GUID, определяющий модель. Поставщики, не использующие идентификаторы GUID для определения таблиц, возвращают значение **NULL**.|  
|**MODEL_PMML**|**DBTYPE_WSTR**||XML-представление содержимого модели в формате PMML.|  
|**SIZE**|**DBTYPE_UI4**||Число байтов в XML-строке.|  
|**РАСПОЛОЖЕНИЕ**|**DBTYPE_WSTR**||Расположение XML-файла. Содержит значение **NULL** , если физический файл не используется для хранения.|  
  
 Этот набор строк схемы не отсортирован.  
  
## <a name="restriction-columns"></a>Столбцы ограничений  
 Набор строк DMSCHEMA_MINING_MODEL_XML может быть ограничен столбцами, приведенными в следующей таблице.  
  
|Имя столбца|Индикатор типа|Состояние ограничения|  
|-----------------|--------------------|-----------------------|  
|**MODEL_CATALOG**|**DBTYPE_W**STR|Необязательно.|  
|**MODEL_SCHEMA**|**DBTYPE_WSTR**|Необязательно.|  
|**MODEL_NAME**|**DBTYPE_WSTR**|Необязательно.|  
|**MODEL_TYPE**|**DBTYPE_WSTR**|Необязательно.|  
  
## <a name="see-also"></a>См. также:  
 [Наборы строк схемы интеллектуального анализа данных](../../../analysis-services/schema-rowsets/data-mining/data-mining-schema-rowsets.md)  
  
  
